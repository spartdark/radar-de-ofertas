# Radar de Ofertas Project Memory

Durable memory for the `radar-de-ofertas` project.

## Purpose

Preserve reusable learning from offer research and price comparison workflows so future sessions can build on evidence instead of chat memory.

## Current Adoption State

- AI operating profile: `PROJECT_AI_PROFILE.md`
- Reuse adoption PRD: `docs/specs/adopcion-reuse-promotion-guide/PRD.md`
- Keepa-like discovery PRD: `docs/specs/keepa-like-radar-de-ofertas/PRD.md`
- Memory contract: `knowledge/README.md`
- Reuse candidates: `knowledge/projects/radar-de-ofertas/reuse-backlog.md`
- Source registry: `knowledge/projects/radar-de-ofertas/source-index.md`

## Active Flow

```txt
idea/process -> evidence -> insight -> experiment -> doc/template -> skill -> plugin -> automation
```

## Active Decisions

- Start with project memory and backlog, not skills or plugins.
- Keep the first price-comparison workflow as `knowledge` until at least two manual runs are reviewed.
- Treat prices as time-sensitive evidence, not durable facts.
- Mark missing evidence and assumptions explicitly.
- Treat bank promotion comparison as a separate workflow from simple price comparison because caps, payment rails, MSI, registration, and delayed statement credits change the recommendation.
- Do not combine store coupons, wallet routes, MSI, and bank statement bonuses unless terms or checkout evidence support the stack.

## Open Memory Areas

- Price evidence format.
- Product and SKU normalization rules.
- Store scope.
- Manual QA process for price comparisons.
- Keepa-like wizard of oz experiment for price history and alert demand.
- Criteria for promoting the first workflow to `docs/`.
- Manual bank-promotion comparison runbook candidate after another validated high-ticket run.
