# Reuse Backlog

Reusable candidates for `radar-de-ofertas`.

Use this file before creating docs/templates, skills, plugins, or automations. The default path is to keep a candidate in `knowledge` until evidence and manual validation justify promotion.

## Classification Criteria

| Destination | Use when | Promotion threshold |
|---|---|---|
| `knowledge` | Idea, evidence, insight, experiment, open question, or project memory. | Has enough context to preserve value and traceability. |
| `docs/template` | Repeatable process, checklist, runbook, or starter artifact for people or agents. | At least one validated manual run; preferably two for volatile price workflows. |
| `skill` | Codex should repeatedly execute the same expert workflow. | Clear inputs, outputs, guardrails, validation, and manual run evidence. |
| `plugin` | A skill needs packaged scripts, APIs, tools, assets, integrations, setup, or distribution. | Validated skill or manual workflow plus security and dependency review. |
| `automation` | A recurring workflow can run with limited intervention. | Manual QA passed, failure cases known, logs captured, disable path defined, explicit approval. |

## Promotion Flow

```txt
idea/process -> evidence -> insight -> experiment -> doc/template -> skill -> plugin -> automation
```

## Candidate Template

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

## Comparador Manual De Precios De Bebidas En Mexico

- Status: idea
- Source: comparacion previa de precios visibles en Walmart, Amazon Mexico, Sam's Club y Costco, compartida en chat antes de crear esta memoria.
- Current artifact: respuesta en chat con tabla de hallazgos, precios visibles, links y recomendaciones por tienda.
- Proposed asset: knowledge
- Reuse case: comparar precios de productos especificos entre tiendas mexicanas y recomendar donde comprar con advertencias de disponibilidad, membresia, envio y ubicacion.
- Expected users: comprador final, operador del radar, Codex research agent.
- Inputs: lista de productos, tiendas objetivo, fecha, ubicacion o codigo postal si aplica, reglas de inclusion o exclusion de envio y promociones.
- Outputs: tabla comparativa, mejor precio visto, comparativo rapido, recomendacion por tienda, advertencias y gaps de evidencia.
- Evidence needed: URLs verificadas, timestamp, precio visible, disponibilidad, SKU o presentacion, membresia, envio y cupones incluidos o excluidos.
- Validation needed: repetir el proceso con otra categoria o lista de 5 a 10 productos; revisar si el formato captura restricciones importantes y permite auditar claims.
- Token budget impact: bajo si se guardan indices y evidencia puntual en vez de paginas completas.
- Decision: mantener como `knowledge` hasta validar al menos dos corridas manuales; no promover a `docs/template`, `skill`, `plugin` ni `automation` todavia.
- Open questions: alcance de categorias, tiendas iniciales, evidencia minima obligatoria, reglas de normalizacion por unidad, politica sobre envio y membresia.
- Risks: precios volatiles, SKUs no equivalentes, paginas agotadas, promociones por ubicacion o membresia, URLs que cambian contenido, claims sin timestamp.

## Keepa-Like Radar De Ofertas Para Mexico

- Status: validating
- Source: analisis solicitado de Keepa y especificacion ISCGV++ creada el 2026-05-22.
- Current artifact: `docs/specs/keepa-like-radar-de-ofertas/PRD.md`; resumen en `knowledge/processed/summaries/keepa-analysis-2026-05-22.md`.
- Proposed asset: knowledge
- Reuse case: adaptar el patron de Keepa - historial de precio, contexto de oferta, comparacion y alertas - a un flujo Mexico-first multi-tienda con evidencia auditable.
- Expected users: comprador en Mexico, operador del radar, Codex research agent.
- Inputs: lista de productos, tiendas objetivo, observaciones historicas, evidencia por observacion, reglas de comparabilidad, restricciones de envio/membresia/ubicacion.
- Outputs: reporte de historial y comparacion por producto, decision sugerida, advertencias, gaps de evidencia y posibles solicitudes de alerta.
- Evidence needed: 30 a 50 observaciones manuales con timestamp, URL, precio, disponibilidad, presentacion, tienda, restricciones y evidencia raw o nota verificable.
- Validation needed: corrida wizard of oz con 10 productos, 3 a 5 tiendas y 2 a 4 fechas; fake door de alertas; auditoria de comparabilidad y completitud.
- Token budget impact: medio si se guardan reportes largos; bajo si se indexan fuentes y se cargan solo observaciones comparables.
- Decision: mantener como `knowledge` y `docs/spec`; no promover a `docs/template`, `skill`, `plugin` ni `automation` hasta completar corridas manuales.
- Open questions: categoria inicial, tiendas del experimento, formato operativo de observaciones, politica de envio, umbrales de alerta, recencia minima para precio vigente.
- Risks: automatizacion prematura, scraping sin aprobacion, SKUs no equivalentes, precios personalizados por ubicacion, membresias, alertas ruidosas, dependencia de API externa.

## Comparador Manual De Promociones Bancarias Hot Sale

- Status: validating
- Source: corrida manual Hot Sale 2026 para iPhone 17, iPhone 17 Pro Max y Sonos Sub Mini realizada el 2026-05-25 con Promodescuentos, Amazon, Costco, Sam's, PayPal, Palacio, Liverpool, MacStore y bancos prioritarios.
- Current artifact: `knowledge/processed/insights/hot-sale-iphone-bank-promos-manual-run-2026-05-25.md`; raw evidence under `knowledge/raw/promo-checks/run-2026-05-25-hot-sale-bancos-001/` and `knowledge/raw/price-checks/run-2026-05-25-*`.
- Proposed asset: knowledge, later `docs/template` or runbook after another validation pass.
- Reuse case: comparar compras de alto ticket en Mexico aplicando promociones bancarias, cupones de tienda, MSI, topes, exclusiones de wallets y preferencias del usuario.
- Expected users: comprador final, operador del radar, Codex research agent, futura app `radar-de-ofertas`.
- Inputs: producto objetivo, tiendas permitidas/excluidas, bancos y tarjetas del usuario, preferencia de contado vs MSI, URLs de ofertas, terminos bancarios, screenshots de checkout.
- Outputs: ranking de rutas de compra, precio final estimado, pago inicial, bonificacion esperada, meses, supuestos, nivel de confianza y checklist de validacion antes de pagar.
- Evidence needed: fuentes oficiales de cada banco, screenshots finales de checkout, confirmacion de seller/fulfillment, reglas de stacking por tienda, timestamp y disponibilidad.
- Validation needed: repetir con otro producto de alto ticket o validar esta misma corrida contra terminos oficiales completos de Banorte, Banamex, BBVA, Amex, PayPal y Costco.
- Token budget impact: medio si se cargan todas las promociones; bajo si se indexan promociones como objetos y se cargan solo las rutas candidatas.
- Decision: mantener como `knowledge`; no promover a skill/plugin/automation. Considerar `docs/runbooks/manual-bank-promo-comparison.md` tras una corrida adicional o validacion oficial.
- Open questions: como modelar stacking incierto, como ponderar MSI vs descuento contado, como valorar riesgo de bonificacion diferida, si Sam's debe heredar exclusion de Walmart Mexico, como evitar recomendaciones por padding artificial de carrito, y como comparar tiendas que cambian el precio base entre contado, banco directo y wallet/PayPal.
- Risks: promociones volatiles, terminos incompletos en fuentes secundarias, caps mal interpretados, wallet/MSI excluido, cupones agotados, compras divididas, evidencia personalizada por usuario o membresia.

## Watchlist Manual De Ofertas Visibles

- Status: validating
- Source: barrido Sam's + Costco del 2026-05-26 y `knowledge/projects/radar-de-ofertas/offer-watchlist.md`.
- Current artifact: `knowledge/projects/radar-de-ofertas/offer-watchlist.md`; raw evidence under `knowledge/raw/price-checks/run-2026-05-26-sams-costco-ofertas-001/`; summary in `knowledge/processed/summaries/sams-costco-offer-sweep-2026-05-26.md`.
- Proposed asset: knowledge
- Reuse case: separar productos con senales visibles de descuento de recomendaciones reales de compra, priorizando que articulos merecen recheck o comparacion historica.
- Expected users: comprador final, operador del radar, Codex research agent, futura app `radar-de-ofertas`.
- Inputs: tienda, categoria, pagina fuente, timestamp, precio actual, precio previo o ahorro visible, disponibilidad, envio, membresia, review signal y notas de comparabilidad.
- Outputs: watchlist segmentada en `strong_signal`, `candidate_to_track`, `watch_with_caution` y `not_a_deal_yet`; siguientes validaciones por producto.
- Evidence needed: product pages exactas, historial o competidores same-SKU, costo de membresia/envio, checkout final si es alto ticket, y baseline confiable del precio anterior.
- Validation needed: recheck de 5 a 10 productos del watchlist contra competidores o historial; medir cuantos `strong_signal` sobreviven como recomendaciones.
- Token budget impact: bajo si se mantiene como tabla resumida y las observaciones completas quedan en raw CSV.
- Decision: mantener como `knowledge`; no promover a doc/template hasta validar que la rubrica predice ofertas reales y no solo descuentos visibles.
- Open questions: umbral por categoria, peso de reviews, regla de membresia para no socios, si exigir same-SKU antes de `strong_signal`, y como registrar precio historico.
- Risks: descuentos inflados por MSRP, productos no comparables, baja calidad a pesar de descuento, stock limitado, precios por ubicacion o membresia, y confundir MSI con ahorro real.

## Modelo De Rutas Y Promociones Bancarias

- Status: idea
- Source: corridas Hot Sale 2026 de iPhone, Sonos Sub Mini, Apple TV y Sam's Club bank routes.
- Current artifact: `knowledge/processed/insights/hot-sale-iphone-bank-promos-manual-run-2026-05-25.md`; summaries and raw evidence under `knowledge/raw/promo-checks/` and `knowledge/raw/price-checks/run-2026-05-25-*`.
- Proposed asset: knowledge
- Reuse case: representar promociones bancarias como objetos comparables antes de calcular una ruta de compra.
- Expected users: operador del radar, Codex research agent, futura app `radar-de-ofertas`.
- Inputs: banco, tarjeta, tipo de tarjeta, canal, tienda participante, minimo de compra, porcentaje o monto, tope, registro, MSI, forma de pago, exclusiones, acumulacion, fechas, evidencia y confianza.
- Outputs: objeto de promocion normalizado, reglas de elegibilidad, calculo de beneficio estimado, bloqueos de validacion y advertencias de stacking.
- Evidence needed: terminos oficiales de bancos, evidencia de checkout cuando aplique, confirmacion de seller/fulfillment, y screenshots o notas de carrito final para compras de alto valor.
- Validation needed: normalizar al menos 5 promociones reales y reproducir manualmente una recomendacion ya trabajada sin mezclar rutas incompatibles.
- Token budget impact: medio si se cargan terminos largos; bajo si se guardan objetos compactos con links a fuente.
- Decision: mantener como `knowledge`; puede alimentar un runbook, pero no skill/plugin/automation sin validacion adicional.
- Open questions: valor financiero de MSI vs contado, manejo de bonificaciones diferidas, rangos cuando el stacking es incierto, y tratamiento de rewards tipo Cashi frente a cashback.
- Risks: terminos incompletos, beneficios no acumulables, exclusiones de wallets, compras partidas, topes diarios vs campana, registro tardio y evidencia personalizada.
