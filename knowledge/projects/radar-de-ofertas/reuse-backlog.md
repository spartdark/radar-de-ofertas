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
