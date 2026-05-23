# PRD

## 0. Metadata
- Nombre del problema: Adoptar Reuse Promotion Guide para Radar de Ofertas sin promover prematuramente assets.
- Slug: adopcion-reuse-promotion-guide
- Fecha: 2026-05-22
- Autor del analisis: Codex usando ISCGV++
- Estado: Draft para adopcion
- Decision recomendada: Avanzar con adopcion minima de memoria y backlog; no crear skills, plugins ni automations hasta validar corridas manuales.

## 1. Resumen Ejecutivo
- Problema: El proyecto tiene hallazgos, procesos y aprendizajes utiles sobre comparacion de precios, pero todavia no tiene memoria durable ni reglas para decidir que debe quedarse como conocimiento, documento, skill, plugin o automation.
- Usuario objetivo: Operador del proyecto `radar-de-ofertas` que usa Codex para investigar, documentar y eventualmente reutilizar workflows de deteccion de ofertas en Mexico.
- Oportunidad: Convertir comparaciones manuales de precios en memoria reusable trazable, empezando por un backlog ligero antes de construir capacidades mas pesadas.
- Por que ahora: El repo esta vacio y puede adoptar una estructura limpia desde el inicio, sin deuda documental ni migraciones.
- Riesgo principal: Saltar de un analisis aislado a una skill, plugin o automation sin evidencia suficiente, generando assets fragiles o poco confiables.

## 2. Scoreboard Global
| Fase | Claridad | Completitud | Riesgo | Validabilidad | Decision |
|------|----------|-------------|--------|---------------|----------|
| Gate 1 - Intent Engineering | 4 | 4 | 4 | 4 | Avanzar |
| Gate 2 - Spec Engineering | 4 | 4 | 4 | 4 | Avanzar |
| Gate 3 - Context Engineering | 4 | 4 | 3 | 4 | Avanzar |
| Gate 4 - Generation Control | 4 | 3 | 3 | 4 | Avanzar |
| Gate 5 - Validation Engineering | 4 | 4 | 4 | 4 | Avanzar |
| Gate 6 - Arquitectura AI-First | 4 | 3 | 3 | 4 | Avanzar con alcance minimo |

## 3. Gate 1 - Intent Engineering
### 3.1 Entregable del Intent Agent

El objetivo real no es construir un radar automatizado todavia. El objetivo inmediato es crear una memoria reusable del proyecto para que ideas, procesos, prompts, aprendizajes y workflows de comparacion de ofertas puedan madurar con evidencia antes de promoverse.

Hechos verificados:
- El repo local `/Users/vladimir.saldivar/Documents/radar-de-ofertas` solo contiene `.git`.
- No existen `AGENTS.md`, `PROJECT_AI_PROFILE.md`, `knowledge/`, `docs/`, `skills/`, `plugins/` ni equivalentes.
- El trabajo previo incluye una comparacion manual de precios visibles en linea en Mexico para bebidas alcoholicas y cervezas.

Problema formulado:
- Sin memoria durable, los aprendizajes quedan atrapados en chat.
- Sin backlog de reutilizacion, no hay criterio para decidir si un hallazgo debe ser conocimiento, documentacion, skill, plugin o automation.
- Sin evidencia minima, los precios y recomendaciones pueden quedar desactualizados o no verificables.

### 3.2 JTBD

Funcional:
- Cuando investigue ofertas, quiero guardar evidencia, aprendizajes y candidatos reutilizables para poder repetir o mejorar el proceso sin depender de memoria de chat.

Emocional:
- Quiero confianza en que las recomendaciones de ofertas no son ocurrencias ni snapshots imposibles de auditar.

Social:
- Quiero que otro operador o agente pueda entender por que una comparacion fue confiable, que falta validar y cuando conviene promoverla.

### 3.3 Supuestos criticos
- El proyecto seguira usando Codex como asistente principal de investigacion y documentacion.
- El project id inicial sera `radar-de-ofertas`.
- La primera unidad reusable sera el workflow de comparacion manual de precios visibles en tiendas mexicanas.
- Se aceptara una adopcion minima antes de copiar una plantilla completa del playbook.
- La evidencia puede empezar con URLs y timestamps, aunque despues podria requerir screenshots, HTML o exports.

### 3.4 Auditoria

El problema esta separado de la solucion. La solucion minima propuesta es memoria y backlog, no automatizacion. La urgencia esta justificada por el estado vacio del repo y por el riesgo de perder trazabilidad del trabajo previo. La debilidad principal es que todavia no hay fuentes persistidas localmente ni una segunda corrida manual para confirmar repetibilidad.

### 3.5 Scores
- Claridad: 4
- Completitud: 4
- Riesgo: 4
- Validabilidad: 4

### 3.6 Decision

Avanzar. Hay suficiente claridad para documentar una adopcion minima y registrar el primer candidato sin construir assets avanzados.

## 4. Gate 2 - Spec Engineering
### 4.1 Entregable del Spec Agent

La adopcion minima debe crear una estructura documental pequena que permita:
- enrutar agentes con reglas cortas;
- registrar perfil, alcance y definicion de terminado del proyecto;
- separar memoria reusable de evidencia cruda;
- registrar candidatos de reutilizacion antes de promoverlos;
- definir criterios para `knowledge`, `docs/template`, `skill`, `plugin` y `automation`.

Archivos candidatos para la adopcion posterior:
- `AGENTS.md`
- `PROJECT_AI_PROFILE.md`
- `knowledge/README.md`
- `knowledge/projects/radar-de-ofertas/README.md`
- `knowledge/projects/radar-de-ofertas/reuse-backlog.md`
- `knowledge/projects/radar-de-ofertas/source-index.md`

### 4.2 User stories

- Como operador del radar, quiero que el repo tenga un `AGENTS.md` corto para que Codex sepa donde buscar memoria, comandos y restricciones.
- Como operador del radar, quiero un `PROJECT_AI_PROFILE.md` para declarar alcance, fuentes, criterios de terminado y riesgos.
- Como operador del radar, quiero un `reuse-backlog.md` para capturar candidatos reutilizables antes de convertirlos en docs, skills, plugins o automations.
- Como operador del radar, quiero clasificar cada candidato por evidencia, inputs, outputs y validacion necesaria para evitar promociones prematuras.
- Como operador del radar, quiero distinguir precios dinamicos, conocimiento estable y memoria de proyecto para reducir alucinaciones.

### 4.3 Criterios GIVEN / WHEN / THEN

- GIVEN que el repo esta vacio, WHEN se adopte la guia, THEN debe existir una estructura minima de memoria sin crear skills, plugins ni automations.
- GIVEN un nuevo hallazgo de precios, WHEN se quiera guardar aprendizaje reusable, THEN debe registrarse en `knowledge/projects/radar-de-ofertas/reuse-backlog.md` con estado, evidencia y validacion.
- GIVEN un workflow repetido, WHEN haya al menos dos corridas manuales revisadas, THEN puede considerarse promocion a `docs/` o `templates/`.
- GIVEN una propuesta de skill, plugin o automation, WHEN falten inputs, outputs, guardrails o validacion manual, THEN la promocion debe bloquearse.
- GIVEN una recomendacion de compra, WHEN se use como evidencia, THEN debe incluir fuente, timestamp, precio visible, disponibilidad y advertencias de membresia, envio o ubicacion.

### 4.4 Trazabilidad problema -> feature -> metrica

| Problema | Feature documental | Metrica o senal |
|---|---|---|
| Aprendizajes atrapados en chat | `knowledge/projects/radar-de-ofertas/reuse-backlog.md` | Cada candidato tiene estado, fuente, decision y validacion |
| Promocion prematura a skills/plugins | Criterios de clasificacion | Ningun asset avanzado se crea sin corrida manual validada |
| Evidencia volatil de precios | `source-index.md` y reglas de evidencia | Cada comparacion referencia URLs, fecha y restricciones |
| Contexto excesivo para Codex | `AGENTS.md` corto y rutas claras | Codex puede cargar indices antes de fuentes largas |
| Falta de definicion del proyecto | `PROJECT_AI_PROFILE.md` | Alcance, no objetivos y done condition quedan explicitos |

### 4.5 Definicion de MVP como experimento

MVP experimental:
- Crear solo la base documental minima.
- Registrar el primer candidato: `Comparador Manual De Precios De Bebidas En Mexico`.
- Ejecutar una segunda comparacion manual en otra lista de productos o categoria.
- Evaluar si el backlog ayuda a decidir que conservar, que validar y que no promover.

No objetivos del MVP:
- No crear scrapers.
- No automatizar monitoreo.
- No crear skills.
- No crear plugins.
- No prometer precios en tiempo real.

### 4.6 Auditoria

La especificacion mantiene el MVP como experimento y no como backlog recortado de una plataforma completa. Los criterios de aceptacion son verificables. La trazabilidad entre problema, archivo y metrica es suficiente para adopcion inicial. Falta definir formato exacto de evidencia cruda, pero puede quedar como pregunta abierta sin bloquear.

### 4.7 Scores
- Claridad: 4
- Completitud: 4
- Riesgo: 4
- Validabilidad: 4

### 4.8 Decision

Avanzar. La especificacion es implementable con cambios pequenos y reversibles.

## 5. Gate 3 - Context Engineering
### 5.1 Entregable del Context Agent

El sistema debe separar contexto estable, datos dinamicos y memoria de usuario/proyecto. La comparacion de precios mezcla datos altamente volatiles con aprendizajes reutilizables; por eso no deben vivir en el mismo nivel documental.

### 5.2 Conocimiento estable

Debe vivir en:
- `AGENTS.md`: reglas de carga, rutas de memoria y restricciones.
- `PROJECT_AI_PROFILE.md`: objetivo del proyecto, alcance, fuentes permitidas, definicion de terminado.
- `knowledge/README.md`: contrato de memoria y promocion.
- `docs/` futuros: runbooks, checklists y plantillas una vez validados.

Contenido estable inicial:
- Flujo de promocion: `idea/proceso -> evidencia -> insight -> experimento -> doc/template -> skill -> plugin -> automation`.
- Criterios de clasificacion de assets.
- Reglas de no promocion prematura.

### 5.3 Datos dinamicos

Debe vivir en:
- `knowledge/raw/price-checks/` para evidencia cruda.
- `knowledge/projects/radar-de-ofertas/source-index.md` para registrar fuente, fecha, producto, tienda y restricciones.

Datos dinamicos:
- precios visibles;
- disponibilidad;
- descuentos;
- URLs de producto;
- condiciones de envio;
- membresia;
- cupones;
- ubicacion o codigo postal;
- fecha y hora de consulta.

### 5.4 Memoria de usuario

Debe vivir en:
- `knowledge/projects/radar-de-ofertas/reuse-backlog.md`
- `knowledge/projects/radar-de-ofertas/README.md`

Memoria inicial:
- El usuario quiere adoptar Reuse Promotion Guide sin saltar directo a skills o plugins.
- El primer dominio observado es comparacion de precios online en Mexico.
- El primer ejemplo contiene categorias como licor, whisky, vodka, cerveza y vino.

### 5.5 Estrategia RAG

No se requiere RAG tecnico en el MVP. La estrategia inicial es filesystem memory:
- cargar `AGENTS.md` primero;
- cargar `PROJECT_AI_PROFILE.md` cuando la tarea toque alcance o validacion;
- cargar `reuse-backlog.md` para candidatos reutilizables;
- cargar `source-index.md` antes de evidencia cruda;
- cargar raw evidence solo cuando se necesite verificar un precio o claim.

Si el volumen crece, se podria evaluar indexacion por:
- tienda;
- categoria;
- producto;
- fecha;
- tipo de evidencia;
- confiabilidad.

### 5.6 Riesgos de alucinacion y context window

Riesgos:
- Tratar precios antiguos como actuales.
- Mezclar productos o SKUs similares.
- Concluir que una tienda gana sin normalizar volumen, paquete, membresia o envio.
- Citar URLs que ya cambiaron de contenido.
- Cargar demasiada evidencia cruda y perder instrucciones importantes.

Mitigaciones:
- Guardar timestamps.
- Separar hechos verificados, inferencias y supuestos.
- Exigir normalizacion por unidad cuando aplique.
- Usar source index antes de raw evidence.
- Mantener archivos de memoria concisos.

### 5.7 Auditoria

La separacion entre conocimiento estable, datos dinamicos y memoria del proyecto esta clara. La estrategia evita RAG prematuro y usa archivos como memoria durable. El riesgo tecnico mayor es que las fuentes comerciales cambian rapido; la mitigacion depende de disciplina de evidencia, no de tecnologia.

### 5.8 Scores
- Claridad: 4
- Completitud: 4
- Riesgo: 3
- Validabilidad: 4

### 5.9 Decision

Avanzar. El diseno de contexto es suficiente para adopcion minima, con riesgo controlado por evidencia y timestamps.

## 6. Gate 4 - Generation Control
### 6.1 Entregable del Generation Agent

Todo candidato de reutilizacion debe registrarse con campos estructurados. Las salidas de comparacion de precios deben ser auditables y no presentarse como verdad permanente.

### 6.2 Output contracts

Contrato para `reuse-backlog.md`:

```md
## <Candidate Name>

- Status: idea | validating | ready | promoted | dropped
- Source:
- Current artifact:
- Proposed asset: knowledge | docs/template | skill | plugin | automation
- Reuse case:
- Expected users:
- Inputs:
- Outputs:
- Evidence needed:
- Validation needed:
- Token budget impact:
- Decision:
- Open questions:
- Risks:
```

Contrato para comparacion de precios:

```md
## <Run Name>

- Date checked:
- Location assumptions:
- Stores checked:
- Products checked:
- Evidence:
- Normalization rules:
- Exclusions:
- Findings:
- Confidence:
- Validation gaps:
```

### 6.3 JSON schemas

No se requiere JSON schema para el MVP documental. Si despues se automatiza captura o validacion, se recomienda definir un schema para price checks:

```json
{
  "product": "string",
  "store": "string",
  "url": "string",
  "checked_at": "ISO-8601 datetime",
  "visible_price_mxn": "number",
  "package_size": "string",
  "availability": "string",
  "membership_required": "boolean",
  "shipping_included": "boolean",
  "confidence": "verified | inferred | experimental | unverified",
  "notes": "string"
}
```

### 6.4 Guardrails

- No crear skills, plugins ni automations desde un solo ejemplo.
- No presentar precios como actuales sin fecha de consulta.
- No mezclar productos con distinto volumen o paquete sin normalizar.
- No usar resumenes como evidencia primaria cuando la fuente importa.
- No guardar secretos, sesiones, cookies ni datos personales en evidencia.
- No automatizar scraping sin revisar terminos, estabilidad y manejo de errores.

### 6.5 Validacion de outputs

Checklist minima:
- El candidato tiene estado y decision.
- La fuente esta referenciada.
- La evidencia faltante esta marcada.
- El tipo de asset propuesto esta justificado.
- Hay input, output y done condition.
- Hay criterios de falsificacion o validacion.
- Las inferencias estan separadas de hechos verificados.

### 6.6 Evals

Evals manuales iniciales:
- Dado un analisis de precios, un lector puede identificar que claims son verificados y cuales son supuestos.
- Dado un candidato en backlog, Codex puede decidir si debe quedarse en knowledge o promoverse.
- Dado un precio citado, se puede encontrar su URL, fecha y restriccion.
- Dado un workflow propuesto como skill, se puede comprobar que hubo al menos una corrida manual validada.

### 6.7 Auditoria

Los contratos son concretos para documentacion y comparacion de precios. JSON schema queda explicitamente fuera del MVP, lo cual reduce complejidad. El punto debil es que la validacion automatica no existe todavia; para esta fase es aceptable porque el objetivo es adopcion documental.

### 6.8 Scores
- Claridad: 4
- Completitud: 3
- Riesgo: 3
- Validabilidad: 4

### 6.9 Decision

Avanzar. Los contratos son suficientes para crear memoria reusable sin sobreconstruir.

## 7. Gate 5 - Validation Engineering
### 7.1 Entregable del Validation Agent

La validacion debe probar dos cosas:
- que el problema existe: el trabajo reusable se pierde o queda ambiguo si vive solo en chat;
- que la solucion minima ayuda: el backlog y la memoria reducen ambiguedad y evitan promociones prematuras.

### 7.2 Hipotesis clave

- H1: Un `reuse-backlog.md` permite capturar candidatos reutilizables con menos ambiguedad que dejarlos en chat.
- H2: La clasificacion `knowledge | docs/template | skill | plugin | automation` evita crear assets demasiado pesados antes de validar workflows.
- H3: Registrar evidencia minima de precios mejora la confianza y auditabilidad de recomendaciones.
- H4: Un `AGENTS.md` corto y un `PROJECT_AI_PROFILE.md` reducen contexto repetido en sesiones futuras.

### 7.3 Experimentos

Experimento 1: Backlog inicial
- Smallest test: Crear el candidato `Comparador Manual De Precios De Bebidas En Mexico` en `reuse-backlog.md`.
- Success signal: El candidato tiene estado, evidencia faltante, validacion requerida y decision clara.
- Failure signal: El candidato no ayuda a decidir si promover o descartar.

Experimento 2: Segunda corrida manual
- Smallest test: Repetir el workflow con otra lista de 5 a 10 productos o una categoria distinta.
- Success signal: Se puede reutilizar el mismo contrato sin redisenarlo.
- Failure signal: El formato no captura restricciones importantes como ubicacion, envio o SKU.

Experimento 3: Decision de promocion
- Smallest test: Revisar dos corridas manuales y decidir si se queda en knowledge o pasa a `docs/`.
- Success signal: La decision esta justificada por evidencia y no por entusiasmo.
- Failure signal: La promocion sigue siendo subjetiva.

### 7.4 Metricas leading

- Numero de candidatos con estado y decision.
- Porcentaje de comparaciones con URL, timestamp y restricciones.
- Numero de preguntas abiertas reducidas despues de una corrida manual.
- Tiempo para que Codex encuentre contexto relevante sin releer chat.

### 7.5 Metricas lagging

- Numero de workflows promovidos a docs/templates despues de validacion.
- Numero de skills/plugins evitados por falta de evidencia.
- Reutilizacion efectiva del runbook en nuevas investigaciones.
- Reduccion de errores por SKU, volumen, disponibilidad o fecha.

### 7.6 Criterios de falsificacion

- Si despues de dos corridas manuales el backlog no mejora decisiones, detener adopcion y simplificar.
- Si los campos de evidencia son demasiado pesados para usarse, iterar el formato.
- Si los precios no pueden auditarse con URLs y timestamps, no promover el workflow.
- Si el proceso exige contexto excesivo, dividir indices y evidencia cruda.

### 7.7 Umbrales para avanzar, iterar o detener

Avanzar a `docs/template` si:
- existen al menos dos corridas manuales revisadas;
- el formato captura evidencia suficiente;
- el workflow tiene inputs, outputs y done condition claros.

Iterar si:
- faltan restricciones recurrentes;
- los campos son confusos;
- hay dudas sobre normalizacion de precios.

Detener o no promover si:
- no se puede verificar evidencia;
- el proceso no se repite;
- las recomendaciones son demasiado volatiles para ser utiles.

### 7.8 Auditoria

Las hipotesis son falsificables y el MVP esta tratado como experimento. Las metricas evitan vanity metrics y se enfocan en comportamiento del workflow. Falta definir quien revisa la calidad de la segunda corrida manual; por ahora se asume revision humana del operador.

### 7.9 Scores
- Claridad: 4
- Completitud: 4
- Riesgo: 4
- Validabilidad: 4

### 7.10 Decision

Avanzar. Hay suficientes experimentos para validar adopcion sin construir capacidades avanzadas.

## 8. Gate 6 - Arquitectura AI-First
### 8.1 Entregable del Architecture Agent

La arquitectura inicial debe ser filesystem-first, portable y de bajo contexto. No debe introducir dependencias, scripts, scraping ni automatizaciones hasta que el proceso manual demuestre valor.

### 8.2 Separacion de estados

- Estado estable: reglas, perfil, criterios y contratos.
- Estado dinamico: precios, disponibilidad, timestamps, URLs.
- Estado de promocion: backlog de candidatos y decisiones.
- Estado experimental: corridas manuales, resultados y validaciones.

### 8.3 Modularidad y desacoplamiento

Modulos documentales propuestos:
- `AGENTS.md`: routing y reglas cortas.
- `PROJECT_AI_PROFILE.md`: alcance y definicion de terminado.
- `knowledge/README.md`: contrato de memoria.
- `knowledge/projects/radar-de-ofertas/reuse-backlog.md`: candidatos.
- `knowledge/projects/radar-de-ofertas/source-index.md`: fuentes y evidencia.

El diseno permite agregar `docs/`, `skills/`, `plugins/` o automation despues sin reestructurar lo inicial.

### 8.4 Seguridad por defecto

- No guardar credenciales, cookies, sesiones ni datos personales.
- No automatizar acceso a tiendas sin revision de terminos y limites.
- No depender de cuentas personales para evidencia reusable.
- Marcar ubicacion, membresia y envio como restricciones, no como datos universales.

### 8.5 Portabilidad

La estructura propuesta es compatible con el playbook de referencia y puede moverse a otro repo. Se evita lock-in tecnico porque el primer paso es Markdown y memoria filesystem.

### 8.6 Riesgos tecnicos

- Paginas de ecommerce dinamicas o bloqueadas.
- Cambios de precio frecuentes.
- URLs que cambian contenido.
- Productos con nombres similares y SKUs distintos.
- Evidencia cruda que crece sin indice.

### 8.7 Riesgos OWASP LLM

Riesgos aplicables:
- Prompt injection en contenido web de tiendas o paginas externas.
- Overreliance en outputs del LLM sin verificacion de fuente.
- Data leakage si se guardan datos de cuenta o ubicacion precisa.
- Insecure plugin/tool design si se automatiza scraping prematuramente.

Mitigaciones:
- Tratar contenido web como no confiable.
- Guardar evidencia y separar inferencias.
- No usar herramientas autenticadas en MVP.
- Revisar seguridad antes de cualquier plugin o automation.

### 8.8 Auditoria

La arquitectura es deliberadamente minima y portable. La principal brecha es que no define todavia comandos de build/test porque el repo no tiene aplicacion. Eso no bloquea la adopcion documental, pero debe quedar registrado en `PROJECT_AI_PROFILE.md` cuando se cree.

### 8.9 Scores
- Claridad: 4
- Completitud: 3
- Riesgo: 3
- Validabilidad: 4

### 8.10 Decision

Avanzar con alcance minimo. No introducir componentes tecnicos hasta validar el flujo manual.

## 9. Riesgos Consolidados

- Precios y disponibilidad cambian por fecha, codigo postal, membresia, envio y promociones.
- Algunos enlaces del analisis previo podrian apuntar a productos no equivalentes o paginas genericas.
- El proyecto aun no define si cubre solo bebidas o cualquier oferta.
- La evidencia minima todavia no esta persistida localmente.
- Automatizar demasiado pronto podria producir recomendaciones incorrectas o fragiles.
- Guardar demasiada evidencia cruda sin indice podria volver inutil la memoria.
- Las paginas externas pueden contener contenido no confiable para un LLM.

## 10. Supuestos Abiertos

- `radar-de-ofertas` sera el project id inicial.
- La adopcion copiara solo estructura minima, no todo el playbook.
- El primer candidato reusable sera el comparador manual de precios de bebidas en Mexico.
- El usuario aceptara validar manualmente al menos una segunda corrida antes de promover a docs/template.
- El proyecto puede empezar sin comandos de build/test porque todavia no hay aplicacion.

## 11. Preguntas Pendientes

- El radar cubrira solo bebidas o todas las categorias de ofertas?
- Que evidencia minima sera obligatoria: URL, timestamp, screenshot, HTML, precio por unidad o todo lo anterior?
- Se debe guardar evidencia cruda localmente o solo indices con enlaces?
- Que tiendas quedan dentro del alcance inicial?
- Se debe considerar envio, membresia y cupones bancarios o excluirlos por defecto?
- Quien revisa una corrida manual antes de promover el workflow?
- Cual es el umbral para considerar que una recomendacion es suficientemente confiable?

## 12. Recomendacion Final

Avanzar con adopcion minima.

La siguiente accion recomendada es crear la estructura base de memoria y documentacion, no una skill ni un plugin. El primer asset reusable debe quedarse como `knowledge` en `knowledge/projects/radar-de-ofertas/reuse-backlog.md` con estado `idea` o `validating`.

Entrada inicial sugerida para el backlog:

```md
## Comparador Manual De Precios De Bebidas En Mexico

- Status: idea
- Source: comparacion previa de precios visibles en Walmart, Amazon Mexico, Sam's Club y Costco
- Current artifact: respuesta en chat con tabla de hallazgos y URLs
- Proposed asset: knowledge
- Reuse case: comparar precios de productos especificos entre tiendas mexicanas y recomendar donde comprar
- Expected users: comprador final, operador del radar, Codex research agent
- Inputs: lista de productos, tiendas objetivo, fecha, ubicacion o codigo postal si aplica
- Outputs: tabla comparativa, mejor precio visto, advertencias de disponibilidad, recomendacion por tienda
- Evidence needed: URLs verificadas, timestamp, precio visible, disponibilidad, membresia, envio y cupones excluidos o incluidos
- Validation needed: repetir el proceso con otra categoria o lista y confirmar que los precios siguen trazables
- Token budget impact: bajo si se guardan indices y no paginas completas
- Decision: mantener como knowledge hasta validar dos corridas manuales
- Open questions: alcance de categorias, evidencia minima, tiendas iniciales, reglas de normalizacion
- Risks: precios volatiles, SKUs no equivalentes, paginas agotadas, promociones por ubicacion o membresia
```

Criterios de aceptacion para considerar adoptada la guia:
- Existe `AGENTS.md` con rutas de memoria y reglas cortas.
- Existe `PROJECT_AI_PROFILE.md` con objetivo, alcance, restricciones y definicion de terminado.
- Existe `knowledge/README.md` con contrato de memoria.
- Existe `knowledge/projects/radar-de-ofertas/reuse-backlog.md` con el primer candidato registrado.
- Existe una regla explicita para clasificar candidatos como `knowledge`, `docs/template`, `skill`, `plugin` o `automation`.
- Existe un flujo documentado: `idea/proceso -> evidencia -> insight -> experimento -> doc/template -> skill -> plugin -> automation`.
- Hay preguntas abiertas, riesgos y validacion necesaria antes de promover assets.
- No se han creado skills, plugins ni automations sin validacion manual previa.
