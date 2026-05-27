# Radar de Ofertas Project Memory

Durable memory for the `radar-de-ofertas` project.

## Purpose

Preserve reusable learning from offer research and price comparison workflows so future sessions can build on evidence instead of chat memory.

## Current Adoption State

- AI operating profile: `PROJECT_AI_PROFILE.md`
- Reuse adoption PRD: `docs/specs/adopcion-reuse-promotion-guide/PRD.md`
- Keepa-like discovery PRD: `docs/specs/keepa-like-radar-de-ofertas/PRD.md`
- Memory contract: `knowledge/README.md`
- Work log: `knowledge/projects/radar-de-ofertas/work-log.md`
- Reuse candidates: `knowledge/projects/radar-de-ofertas/reuse-backlog.md`
- Source registry: `knowledge/projects/radar-de-ofertas/source-index.md`
- Offer watchlist: `knowledge/projects/radar-de-ofertas/offer-watchlist.md`

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
- For Sam's Club and similar merchants with possible contado vs bank/MSI price bases, compare final checkout totals by route before applying bank bonuses. Track `contado`, `bank direct`, and `wallet/PayPal` as separate routes.
- Treat watchlist items as follow-up candidates, not recommendations. A visible discount becomes actionable only after same-SKU, price-history, or checkout validation.

## Worked Threads Captured

| Area | Current memory | Status |
|---|---|---|
| Reuse promotion adoption | `docs/specs/adopcion-reuse-promotion-guide/PRD.md`; `reuse-backlog.md` | adopted as project rules |
| Keepa-like radar concept | `docs/specs/keepa-like-radar-de-ofertas/PRD.md`; `knowledge/processed/summaries/keepa-analysis-2026-05-22.md` | validating as concept |
| Manual price observation | `docs/experiments/manual-price-runbook-001.md`; `knowledge/raw/price-checks/observation-format.md` | draft experiment |
| Beer price run | `knowledge/raw/price-checks/run-2026-05-22-cervezas-001/` | experimental evidence |
| Hot Sale bank comparison | `knowledge/processed/insights/hot-sale-iphone-bank-promos-manual-run-2026-05-25.md` | strong knowledge signal, not promoted |
| Apple TV low-ticket route | `knowledge/processed/summaries/apple-tv-amazon-threshold-2026-05-25.md` | threshold insight |
| Sam's Club bank routes | `knowledge/processed/summaries/sams-club-bank-routes-2026-05-26.md` | route map, needs checkout validation |
| Sam's + Costco offer sweep | `offer-watchlist.md`; `knowledge/processed/summaries/sams-costco-offer-sweep-2026-05-26.md` | tracking candidates |

## Open Memory Areas

- Price evidence format.
- Product and SKU normalization rules.
- Store scope.
- Manual QA process for price comparisons.
- Keepa-like wizard of oz experiment for price history and alert demand.
- Criteria for promoting the first workflow to `docs/`.
- Manual bank-promotion comparison runbook candidate after another validated high-ticket run.
- Category and threshold rules for deciding when a visible discount becomes a true `worth it` recommendation.
- SKU-level checkout evidence for Sam's routes where PayPal may preserve contado pricing while BBVA direct uses a higher MSI price.
- Standard schema for promotion objects: minimum spend, channel, card type, cap, registration, exclusions, payment rails, reward timing, and eligible merchant scope.
