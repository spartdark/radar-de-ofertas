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
- Open questions: como modelar stacking incierto, como ponderar MSI vs descuento contado, como valorar riesgo de bonificacion diferida, si Sam's debe heredar exclusion de Walmart Mexico, y como evitar recomendaciones por padding artificial de carrito.
- Risks: promociones volatiles, terminos incompletos en fuentes secundarias, caps mal interpretados, wallet/MSI excluido, cupones agotados, compras divididas, evidencia personalizada por usuario o membresia.
