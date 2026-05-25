# PRD

## 0. Metadata
- Nombre del problema: Validar un Radar de Ofertas tipo Keepa para compras en Mexico.
- Slug: keepa-like-radar-de-ofertas
- Fecha: 2026-05-22
- Autor del analisis: Codex usando ISCGV++
- Estado: Draft de descubrimiento y validacion; sin implementacion.
- Decision recomendada: Iterar con experimentos manuales y wizard of oz antes de construir producto, scraper, plugin, skill o automation.

## 1. Resumen Ejecutivo
- Problema: Comprar ofertas en Mexico exige saber si un precio actual realmente es bueno, pero el proyecto aun no tiene evidencia suficiente para automatizar tracking, alertas o comparaciones multi-tienda.
- Usuario objetivo: Comprador mexicano u operador del proyecto que compara productos en Amazon Mexico, Walmart, Costco, Sam's Club y otras tiendas, con atencion a precio, disponibilidad, membresia, envio y presentacion.
- Oportunidad: Reusar el patron de Keepa: historial de precios, alertas, graficas y evidencia por producto, adaptado a un flujo Mexico-first y multi-tienda.
- Por que ahora: El repo ya tiene reglas para preservar evidencia y evitar promocion prematura; esta es una buena fase para convertir la idea en experimento medible.
- Riesgo principal: Copiar el producto visible de Keepa sin validar obtencion legal/confiable de datos, normalizacion de SKUs, valor real para usuarios y costos de mantenimiento.

## 2. Scoreboard Global
| Fase | Claridad | Completitud | Riesgo | Validabilidad | Decision |
|------|----------|-------------|--------|---------------|----------|
| Gate 1 - Intent Engineering | 4 | 4 | 3 | 4 | Avanzar |
| Gate 2 - Spec Engineering | 4 | 3 | 3 | 4 | Avanzar como MVP experimental |
| Gate 3 - Context Engineering | 4 | 4 | 3 | 4 | Avanzar |
| Gate 4 - Generation Control | 4 | 3 | 3 | 4 | Avanzar |
| Gate 5 - Validation Engineering | 4 | 4 | 3 | 5 | Iterar con experimentos manuales |
| Gate 6 - Arquitectura AI-First | 3 | 3 | 3 | 3 | Arquitectura conceptual; no construir aun |

## 3. Gate 1 - Intent Engineering
### 3.1 Entregable del Intent Agent

Hechos verificados sobre Keepa:
- Keepa se presenta como un tracker de precios de Amazon que ofrece graficas de historial de precio y alertas de bajada de precio. Fuente: `https://keepa.com/`.
- La extension de Chrome declara que agrega graficas de historial de precio y alertas de bajada/disponibilidad en sitios Amazon soportados, con soporte para Amazon `.mx` entre otros marketplaces. Fuente: Chrome Web Store, `Keepa(TM) - Amazon Price Tracker`.
- La extension de Firefox describe historial para productos Amazon y Marketplace, alertas configurables desde la pagina de producto y uso sin cuenta. Fuente: Mozilla Add-ons, `Keepa.com - Amazon Price Tracker`.
- Keepa mantiene un framework Java para usuarios de su API, con funciones para pedir productos, analizar historial de precio y calcular medias ponderadas. Fuente: `keepacom/api_backend` en GitHub.

Inferencias sobre como funciona Keepa:
- Keepa probablemente opera una base historica por producto Amazon, identificada por ASIN, donde guarda series de tiempo de precio, disponibilidad, vendedores/ofertas y otros metadatos.
- La extension no parece hacer todo el tracking localmente; se comunica con `keepa.com`, pide datos historicos y embebe la grafica dentro de la pagina Amazon.
- Las alertas funcionan como una capa de watches: el usuario define umbral o condicion, el backend compara cambios nuevos contra esos watches y envia notificacion por el canal configurado.
- La API existe para casos mas avanzados, pero usarla implica dependencia comercial, key, limites y costos.

Problema para `radar-de-ofertas`:
- El usuario no solo quiere ver el precio actual; quiere saber si ese precio es historicamente bueno y comparable entre tiendas mexicanas.
- Las tiendas mexicanas tienen fricciones distintas a Amazon: membresia, envio, ubicacion, packs, cupones, disponibilidad local y SKUs no equivalentes.
- Si el proyecto automatiza demasiado pronto, puede generar recomendaciones falsas por comparar productos no equivalentes o precios que ya cambiaron.

Mapa de intencion:
- Resultado funcional buscado: detectar y comparar ofertas reales con historial, contexto y evidencia.
- Resultado emocional buscado: confianza antes de comprar; reducir miedo a caer en falsas promociones.
- Resultado social buscado: poder explicar por que una oferta fue marcada como buena, con fuentes y fecha.
- Decision de producto inicial: imitar el valor de Keepa, no su implementacion interna.

### 3.2 JTBD

Funcional:
- Cuando estoy por comprar un producto, quiero ver si el precio actual es bajo frente a su historial y frente a tiendas comparables, para decidir si compro, espero o busco alternativa.

Emocional:
- Quiero evitar la sensacion de estar comprando por impulso ante una promocion artificial.

Social:
- Quiero poder compartir una recomendacion defendible: precio visto, fecha, tienda, restricciones y por que se considera oferta.

### 3.3 Supuestos criticos
- El usuario objetivo inicial esta en Mexico y acepta tiendas como Amazon Mexico, Walmart, Sam's Club y Costco.
- La primera categoria puede seguir siendo bebidas o productos de consumo, porque ya existe memoria semilla.
- El valor inicial se puede validar sin scraping ni automatizacion: capturando evidencia manual de 20 a 50 observaciones.
- La comparacion historica necesita normalizar producto, presentacion y tienda antes de emitir alertas.
- El proyecto no debe depender de datos privados, cuentas autenticadas ni direcciones personales para el MVP.

### 3.4 Auditoria

La intencion esta formulada como problema de decision de compra, no como deseo de construir un clon. La evidencia publica sobre Keepa es suficiente para entender el patron de valor, pero no prueba su arquitectura interna completa. La mayor ambiguedad es el usuario especifico: comprador final, operador del radar o reseller. Para no bloquear, este PRD asume comprador/operador en Mexico y deja seller analytics fuera del MVP.

### 3.5 Scores
- Claridad: 4
- Completitud: 4
- Riesgo: 3
- Validabilidad: 4

### 3.6 Decision

Avanzar. Hay suficiente claridad para especificar un MVP experimental, siempre que no se construya automatizacion todavia.

## 4. Gate 2 - Spec Engineering
### 4.1 Entregable del Spec Agent

Producto propuesto:
- Un radar de ofertas Mexico-first que conserva historial de observaciones por producto canonico, compara precio por unidad entre tiendas y emite una evaluacion trazable de "oferta", "precio normal", "esperar" o "no comparable".

MVP experimental:
- No es una app completa.
- No es un scraper.
- No es una extension.
- Es una corrida manual repetible con una tabla estructurada, un historial minimo y una evaluacion asistida por reglas.

Capacidades visibles del MVP:
- Registro de producto canonico: nombre, marca, variante, tamano, unidad y posibles equivalencias.
- Registro de observacion: tienda, URL, fecha/hora, precio visible, disponibilidad, envio, membresia, cupones, ubicacion asumida y evidencia.
- Historial basico: ultimas observaciones por producto-tienda.
- Evaluacion de oferta: precio actual vs minimo observado, promedio observado, precio por unidad y restricciones.
- Reporte: tabla comparativa con recomendacion y advertencias.

Fuera de alcance:
- Scraping automatico.
- Browser extension.
- Alertas recurrentes.
- Integracion con Keepa API.
- Cuentas autenticadas.
- Compras automaticas.
- Seller analytics, ranking de ventas o Buy Box avanzado.

### 4.2 User stories

- Como comprador, quiero saber si el precio actual de un producto es bajo frente a observaciones anteriores para decidir si compro hoy.
- Como comprador, quiero ver restricciones de membresia, envio y ubicacion para no confundir precio visible con costo real.
- Como operador del radar, quiero capturar evidencia minima por observacion para auditar recomendaciones despues.
- Como operador del radar, quiero marcar productos como no comparables cuando cambian tamano, pack o variante.
- Como operador del radar, quiero probar si usuarios piden alertas antes de construirlas.

### 4.3 Criterios GIVEN / WHEN / THEN

- GIVEN un producto con al menos tres observaciones historicas comparables, WHEN se captura un precio nuevo, THEN el sistema debe calcular posicion frente a minimo, maximo, promedio y precio por unidad.
- GIVEN dos productos con diferente presentacion, WHEN se comparan, THEN la salida debe normalizar por unidad o marcar `no comparable`.
- GIVEN una observacion sin timestamp o URL, WHEN se use para recomendacion, THEN debe quedar marcada como `unverified` y no puede sostener una recomendacion fuerte.
- GIVEN una tienda con membresia requerida, WHEN se reporta un precio, THEN la membresia debe mostrarse como restriccion y no ocultarse.
- GIVEN una alerta propuesta, WHEN no haya al menos una corrida manual exitosa de deteccion de bajada de precio, THEN no se debe promover a automation.

### 4.4 Trazabilidad problema -> feature -> metrica

| Problema | Feature MVP | Metrica o senal |
|---|---|---|
| Falsas ofertas por falta de historial | Historial de observaciones | Porcentaje de recomendaciones con al menos 3 observaciones comparables |
| Comparaciones injustas entre packs | Producto canonico y precio por unidad | Porcentaje de items con unidad normalizada o razon de no comparabilidad |
| Precios volatiles sin evidencia | Observacion con timestamp, URL y evidencia | Porcentaje de observaciones con campos minimos completos |
| Valor no validado de alertas | Fake door de alertas | Clicks o solicitudes de "avisame cuando baje" por producto |
| Riesgo de automatizacion prematura | Manual runbook antes de skill/plugin/automation | Numero de corridas manuales revisadas sin romper reglas de evidencia |

### 4.5 Definicion de MVP como experimento

Experimento MVP:
- Seleccionar 10 productos de una categoria inicial.
- Capturar precios manualmente en 3 a 5 tiendas durante 2 a 4 corridas separadas.
- Generar un reporte "tipo Keepa" por producto con historial textual/tabla, no necesariamente grafica.
- Pedir decision del usuario: comprar, esperar, ignorar, crear alerta.
- Medir si la informacion cambia la decision de compra.

Done del MVP:
- 30 a 50 observaciones con evidencia minima.
- Al menos 70% de productos con normalizacion confiable.
- Al menos 5 casos donde el historial cambie o confirme una decision.
- Lista documentada de fallas: SKU ambiguo, precio agotado, envio, membresia, ubicacion, cupon.

### 4.6 Auditoria

La especificacion mantiene el MVP como aprendizaje, no como app recortada. La principal debilidad es que no hay usuario externo confirmado ni datos historicos suficientes. La solucion evita inventar alertas como feature principal y las convierte en fake door. No hay bloqueo porque el experimento manual puede validar ambos riesgos.

### 4.7 Scores
- Claridad: 4
- Completitud: 3
- Riesgo: 3
- Validabilidad: 4

### 4.8 Decision

Avanzar como MVP experimental. No avanzar a implementacion de producto hasta completar corridas manuales.

## 5. Gate 3 - Context Engineering
### 5.1 Entregable del Context Agent

El sistema necesita separar cuatro capas:
- Conocimiento estable: reglas de evidencia, tiendas soportadas, criterios de comparabilidad, taxonomia de productos.
- Datos dinamicos: observaciones de precio, disponibilidad, envio, membresia, cupones y ubicacion.
- Memoria de usuario/proyecto: categorias de interes, tiendas objetivo, decisiones anteriores, candidatos de reutilizacion.
- Contexto de generacion: instrucciones para reportar ofertas sin exagerar ni ocultar incertidumbre.

### 5.2 Conocimiento estable

- Definicion de producto canonico.
- Definicion de observacion de precio.
- Reglas de comparabilidad: misma marca, variante, volumen/unidad, pack, vendedor y condicion cuando aplique.
- Reglas de confianza: `verified`, `inferred`, `experimental`, `unverified`.
- Reglas de recomendacion: no recomendar fuerte sin evidencia minima.
- Aprendizaje de Keepa: historial + contexto + alerta tiene mas valor que un precio aislado.

### 5.3 Datos dinamicos

- Precio visible.
- Precio por unidad.
- Disponibilidad.
- Fecha y hora de consulta.
- URL.
- Tienda y vendedor.
- Presentacion y paquete.
- Envio incluido o excluido.
- Membresia requerida.
- Cupones o promociones.
- Ubicacion o codigo postal asumido.
- Evidencia visual o nota raw.

### 5.4 Memoria de usuario

- Preferencias de categorias.
- Tiendas que el usuario acepta.
- Tolerancia a membresias.
- Reglas sobre envio.
- Productos watchlist.
- Umbrales de precio deseado.
- Decisiones anteriores: compro, espero, descarto.

### 5.5 Estrategia RAG

No se necesita RAG vectorial para el MVP. La estrategia inicial es memoria estructurada por archivos:
- `knowledge/projects/radar-de-ofertas/source-index.md` para registrar fuentes.
- `knowledge/raw/price-checks/` para evidencia cruda cuando exista.
- `knowledge/processed/summaries/` para analisis de productos o corridas.
- `knowledge/projects/radar-de-ofertas/reuse-backlog.md` para candidatos de promocion.

Si el volumen crece:
- Indexar por producto canonico, tienda, categoria, fecha, confianza y tipo de evidencia.
- Recuperar solo observaciones comparables al generar una recomendacion.
- Separar "precio observado" de "decision generada" para evitar que una conclusion anterior se convierta en hecho.

### 5.6 Riesgos de alucinacion y context window

Riesgos:
- Tratar un precio viejo como vigente.
- Comparar productos parecidos pero no equivalentes.
- Omitir membresia, envio o ubicacion.
- Promediar observaciones de tiendas/vendedores no comparables.
- Generar una alerta como si hubiera monitoreo activo.
- Confundir una inferencia de arquitectura de Keepa con un hecho verificado.

Mitigaciones:
- Cada observacion debe tener timestamp y confianza.
- La salida debe listar gaps.
- Las recomendaciones deben decir "segun observaciones guardadas", no "precio real del mercado".
- Usar labels `No validado aun` y `Supuesto` cuando falte evidencia.
- Mantener resumenes cortos y evidencia raw indexada.

### 5.7 Auditoria

El diseno de contexto respeta las reglas del repo y evita meter todo en prompts largos. La separacion entre observaciones y recomendaciones es critica. La limitacion principal es que aun no hay esquema definitivo ni datasets; debe validarse con una categoria real antes de automatizar.

### 5.8 Scores
- Claridad: 4
- Completitud: 4
- Riesgo: 3
- Validabilidad: 4

### 5.9 Decision

Avanzar con filesystem memory y datos estructurados manuales. No implementar RAG vectorial aun.

## 6. Gate 4 - Generation Control
### 6.1 Entregable del Generation Agent

El sistema debe generar reportes conservadores. El output principal no debe ser "compra aqui" sino una evaluacion trazable con evidencia, calculos y advertencias.

### 6.2 Output contracts

Contrato de observacion:

```json
{
  "observed_at": "2026-05-22T22:57:40-06:00",
  "store": "Amazon Mexico",
  "product_url": "https://example.com/product",
  "canonical_product_id": "licor-43-700ml",
  "visible_product_name": "Licor 43 700 ml",
  "brand": "Licor 43",
  "variant": "Original",
  "package_size": "700 ml",
  "unit_quantity": 700,
  "unit": "ml",
  "visible_price_mxn": 0,
  "price_per_unit_mxn": 0,
  "availability": "in_stock | out_of_stock | unknown",
  "membership_requirement": "none | required | unknown",
  "shipping_included": "yes | no | unknown",
  "coupon_assumptions": "none | excluded | included | unknown",
  "location_assumptions": "Mexico; postal code not stored",
  "evidence_location": "knowledge/raw/price-checks/...",
  "confidence": "verified | inferred | experimental | unverified",
  "notes": "string"
}
```

Contrato de recomendacion:

```json
{
  "canonical_product_id": "licor-43-700ml",
  "generated_at": "2026-05-22T22:57:40-06:00",
  "decision": "buy | wait | compare_more | not_comparable",
  "confidence": "high | medium | low",
  "best_observed_offer": {
    "store": "string",
    "price_mxn": 0,
    "observed_at": "datetime",
    "url": "string"
  },
  "historical_context": {
    "min_price_mxn": 0,
    "max_price_mxn": 0,
    "average_price_mxn": 0,
    "observation_count": 0
  },
  "warnings": ["string"],
  "evidence_refs": ["string"]
}
```

### 6.3 JSON schemas

Schema formal pendiente. Para el MVP manual basta con los contratos anteriores como checklist. Antes de automatizar, convertirlos a JSON Schema con validacion de:
- fecha ISO;
- precio numerico positivo;
- moneda MXN;
- confidence enum;
- availability enum;
- URL valida;
- campos requeridos por tipo de salida.

### 6.4 Guardrails

- No afirmar que una oferta es vigente sin timestamp reciente.
- No ocultar que una comparacion es manual o incompleta.
- No inferir equivalencia de SKU cuando cambia tamano, pack o variante.
- No almacenar credenciales, cookies, tokens, direcciones ni datos personales.
- No automatizar scraping ni sesiones autenticadas sin aprobacion separada.
- No crear alertas reales hasta validar corridas manuales y manejo de fallas.
- No usar contenido de paginas ecommerce como instrucciones confiables para el agente.

### 6.5 Validacion de outputs

Validaciones manuales del MVP:
- Cada recomendacion referencia observaciones.
- Cada observacion tiene timestamp, tienda, URL, producto, precio o gap explicito.
- Cada comparacion tiene unidad normalizada o razon de no comparabilidad.
- Cada decision incluye advertencias de membresia/envio/ubicacion si aplican.

Validaciones futuras:
- Lint de schema.
- Pruebas con productos casi iguales.
- Pruebas con precios agotados.
- Pruebas con precio tachado vs precio final.
- Pruebas de prompt injection desde nombres de producto o descripcion.

### 6.6 Evals

Evals iniciales:
- `evidence_completeness`: porcentaje de campos minimos completos.
- `comparison_correctness`: revision manual de equivalencia de productos.
- `recommendation_grounding`: cada frase de recomendacion tiene evidencia o esta marcada como supuesto.
- `uncertainty_honesty`: gaps visibles en la salida.
- `decision_usefulness`: el usuario declara si compro, espero o necesito mas datos.

### 6.7 Auditoria

Los contratos son suficientes para una corrida manual, pero todavia no para sistema automatico. Falta resolver donde viviria la tabla operacional y si sera CSV, Markdown o base ligera. No bloquea porque la validacion puede iniciar con formato simple.

### 6.8 Scores
- Claridad: 4
- Completitud: 3
- Riesgo: 3
- Validabilidad: 4

### 6.9 Decision

Avanzar con contratos como checklist. Iterar schema formal despues de una corrida real.

## 7. Gate 5 - Validation Engineering
### 7.1 Entregable del Validation Agent

La validacion debe probar primero el problema y la decision de usuario, no la tecnologia. Keepa demuestra que el patron tiene mercado en Amazon, pero no demuestra que `radar-de-ofertas` deba construir lo mismo para tiendas mexicanas.

### 7.2 Hipotesis clave

- H1 Problema: Usuarios en Mexico dudan si un descuento es real y quieren historial antes de comprar.
- H2 Solucion: Un reporte con historial manual, precio por unidad y restricciones mejora decisiones de compra.
- H3 Datos: Se pueden capturar observaciones suficientes sin automatizacion para validar valor.
- H4 Normalizacion: Al menos 70% de productos seleccionados pueden compararse de forma confiable.
- H5 Alertas: Usuarios piden avisos de bajada de precio despues de ver historial, no antes.

### 7.3 Experimentos

Experimento 1 - Wizard of Oz Keepa-like:
- Input: 10 productos de una categoria.
- Metodo: capturar precios manualmente en 3 a 5 tiendas durante 2 a 4 corridas.
- Output: reporte por producto con historial y recomendacion.
- Exito: el usuario cambia o confirma decision en al menos 5 casos con base en el historial.

Experimento 2 - Fake door de alertas:
- Input: reportes generados.
- Metodo: incluir opcion no automatizada "avisame si baja de X".
- Output: numero de solicitudes y umbrales elegidos.
- Exito: al menos 30% de productos revisados reciben una solicitud de alerta o umbral.

Experimento 3 - Comparabilidad:
- Input: productos con packs y variantes similares.
- Metodo: operador decide comparable/no comparable y documenta razon.
- Output: matriz de errores.
- Exito: menos de 15% de comparaciones revisadas tienen error material.

Experimento 4 - Evidencia minima:
- Input: fuente indexada y evidencia cruda de cada observacion.
- Metodo: otro agente intenta auditar 10 observaciones.
- Output: pass/fail por observacion.
- Exito: 80% auditable sin volver a buscar manualmente.

### 7.4 Metricas leading

- Observaciones completas por hora de trabajo.
- Porcentaje de observaciones con evidencia minima.
- Porcentaje de productos normalizados.
- Solicitudes de alerta por producto visto.
- Casos donde historial modifica decision.
- Tiempo para auditar una recomendacion.

### 7.5 Metricas lagging

- Ahorro estimado vs precio normal observado.
- Compras evitadas por falso descuento.
- Reuso del formato en segunda categoria.
- Decision de promocion a `docs/template` despues de dos corridas.
- Costo de mantenimiento por tienda si se automatiza.

### 7.6 Criterios de falsificacion

- Menos de 50% de observaciones tienen evidencia minima completa.
- Menos de 40% de productos pueden normalizarse sin ambiguedad.
- El usuario no cambia ninguna decision tras ver historial.
- La mayoria de precios requiere login, ubicacion personal o condiciones no capturables.
- El tiempo manual por producto vuelve inviable incluso el experimento.
- Las recomendaciones no pueden auditarse sin reconsultar todas las tiendas.

### 7.7 Umbrales para avanzar, iterar o detener

Avanzar a `docs/template`:
- Dos corridas manuales completadas.
- 30 a 50 observaciones.
- 70% o mas de productos normalizados.
- 80% o mas de observaciones auditables.
- Al menos 5 decisiones afectadas por historial.

Iterar en `knowledge`:
- Hay senales de valor, pero faltan observaciones, usuario o formato.

Detener:
- La comparabilidad falla, no hay decisiones afectadas o la evidencia no puede capturarse sin riesgos altos.

### 7.8 Auditoria

La validacion es concreta y falsable. El mayor riesgo es medir interes del operador y confundirlo con interes de mercado. Para reducirlo, despues de una primera corrida interna debe buscarse al menos un usuario externo o una decision real de compra. La tecnologia sigue deliberadamente fuera del experimento.

### 7.9 Scores
- Claridad: 4
- Completitud: 4
- Riesgo: 3
- Validabilidad: 5

### 7.10 Decision

Iterar con experimentos manuales. No construir producto todavia.

## 8. Gate 6 - Arquitectura AI-First
### 8.1 Entregable del Architecture Agent

Arquitectura conceptual futura, condicionada a validacion:

```txt
Sources -> Evidence Capture -> Normalization -> Price Ledger -> Deal Evaluation -> Report / Alert
```

Componentes:
- Evidence Capture: captura manual primero; posible conector por tienda despues.
- Normalization: mapea nombres visibles a productos canonicos.
- Price Ledger: guarda observaciones historicas inmutables.
- Deal Evaluation: compara precio actual con historial y reglas.
- Report Generator: genera salida trazable.
- Alert Engine: solo despues de validar umbrales y fallas.

### 8.2 Separacion de estados

- Estado raw: screenshots, URLs, notas, HTML/export si se aprueba.
- Estado normalizado: observaciones limpias.
- Estado derivado: min, max, promedio, precio por unidad, score de oferta.
- Estado de usuario: watchlist, umbrales, preferencias.
- Estado de decision: recomendaciones generadas y su evidencia.

### 8.3 Modularidad y desacoplamiento

- Conectores de tienda aislados por dominio.
- Normalizador independiente de cada fuente.
- Evaluador de ofertas sin dependencia de navegador.
- Generador de reportes separado de datos raw.
- Alertas desacopladas y apagables.

### 8.4 Seguridad por defecto

- No guardar cookies, sesiones, tokens ni direcciones.
- No ejecutar instrucciones contenidas en paginas de ecommerce.
- No mezclar datos personales con historiales publicos.
- Rate limits y politicas por tienda antes de cualquier automatizacion.
- Logs sin datos sensibles.
- Revision legal/ToS antes de scraping o APIs pagadas.

### 8.5 Portabilidad

- Datos en formatos simples al inicio: Markdown/CSV/JSON.
- IDs canonicos propios, no dependientes solo de URL.
- Separar store-specific IDs de producto canonico.
- Evitar lock-in a Keepa API hasta justificarlo.
- Preferir exportabilidad de observaciones.

### 8.6 Riesgos tecnicos

- Cambios de estructura en sitios ecommerce.
- Bloqueos, captchas, geolocalizacion o precios personalizados.
- Productos equivalentes dificiles de mapear.
- Datos historicos insuficientes para nuevos productos.
- Alertas ruidosas por cambios temporales o stock.
- Costos si se depende de APIs comerciales.

### 8.7 Riesgos OWASP LLM

- Prompt injection desde nombres/descripciones de producto.
- Data poisoning si evidencia manual incorrecta entra al ledger.
- Overreliance: aceptar recomendaciones sin verificar restricciones.
- Sensitive information disclosure si se capturan cuentas o ubicaciones.
- Insecure plugin/tool design si se crean conectores antes de guardrails.
- Excessive agency si el sistema compra, alerta o automatiza sin aprobacion.

### 8.8 Auditoria

La arquitectura conceptual es razonable, pero aun seria prematuro implementarla. La separacion de estados es la decision mas importante que conviene preservar. El riesgo no esta en dibujar componentes, sino en convertirlos en codigo sin datos suficientes y sin revisar fuentes permitidas.

### 8.9 Scores
- Claridad: 3
- Completitud: 3
- Riesgo: 3
- Validabilidad: 3

### 8.10 Decision

Mantener como referencia conceptual. No construir hasta pasar Gate 5 con datos reales.

## 9. Riesgos Consolidados

- Copiar Keepa como feature set sin validar problema Mexico-first.
- Scraping o automatizacion sin aprobacion, ToS review ni manejo de fallas.
- Comparar SKUs no equivalentes.
- Recomendaciones con precios viejos.
- Ignorar envio, membresia, cupones o ubicacion.
- Confundir evidencia publica de Keepa con conocimiento de su arquitectura interna.
- Dependencia prematura de API externa.
- Alertas con falsos positivos.
- Captura accidental de datos sensibles.
- Prompt injection desde contenido ecommerce.

## 10. Supuestos Abiertos

- El usuario inicial acepta un flujo manual antes de automatizar.
- Bebidas o productos de consumo siguen siendo categoria inicial adecuada.
- Las tiendas objetivo permiten suficiente evidencia publica sin login.
- El valor principal es decision de compra, no seller analytics.
- Un historial pequeno de observaciones puede generar senales utiles.

## 11. Preguntas Pendientes

- Que categoria se usara para la primera corrida Keepa-like?
- Cuales tiendas entran en el primer experimento?
- Cuantas observaciones por producto bastan para recomendar?
- Se considerara envio dentro del precio final o como advertencia separada?
- Que tan reciente debe ser un precio para considerarse vigente?
- El usuario quiere alertas por umbral absoluto, porcentaje de descuento o minimo historico?
- Se permite usar APIs pagadas en una fase futura?

## 12. Recomendacion Final

Decision recomendada: iterar, no construir aun.

Siguiente paso recomendado:
- Ejecutar una corrida manual wizard of oz con 10 productos, 3 a 5 tiendas y 2 a 4 fechas de captura.
- Guardar observaciones con evidencia minima en `knowledge/raw/price-checks/` y registrar fuentes en `knowledge/projects/radar-de-ofertas/source-index.md`.
- Solo despues de dos corridas auditables, evaluar promocion a `docs/template`.

## 13. Fuentes Consultadas

- Keepa homepage: `https://keepa.com/`
- Chrome Web Store, Keepa(TM) - Amazon Price Tracker: `https://chromewebstore.google.com/detail/keepa-amazon-price-tracke/neebplgakaahbhdphmkckjjcegoiijjo`
- Mozilla Add-ons, Keepa.com - Amazon Price Tracker: `https://addons.mozilla.org/en-US/firefox/addon/keepa/`
- Keepa API Java Framework: `https://github.com/keepacom/api_backend`
- Python Keepa client documentation, usada solo como evidencia secundaria de uso de API: `https://keepaapi.readthedocs.io/`
