# Radar de Ofertas Work Log

Chronological durable memory for work already performed. This is a navigation aid, not primary evidence. Use `source-index.md` and raw folders for audit details.

## 2026-05-22 - Reuse Promotion Guide Adopted

- Work performed: created the project memory structure, adoption PRD, project profile, memory contract, reuse backlog, and source index.
- Durable outputs:
  - `AGENTS.md`
  - `PROJECT_AI_PROFILE.md`
  - `docs/specs/adopcion-reuse-promotion-guide/PRD.md`
  - `knowledge/README.md`
  - `knowledge/projects/radar-de-ofertas/reuse-backlog.md`
  - `knowledge/projects/radar-de-ofertas/source-index.md`
- Learning: the project should start with evidence and small reusable memory; no skills, plugins, scraping, or automations until manual workflows are validated.
- Confidence: verified for repository artifacts; experimental for the first reusable workflow.

## 2026-05-22 - Keepa Pattern Researched

- Work performed: researched Keepa's public product pattern and turned it into a Mexico-first radar concept.
- Durable outputs:
  - `docs/specs/keepa-like-radar-de-ofertas/PRD.md`
  - `knowledge/processed/summaries/keepa-analysis-2026-05-22.md`
  - source entry `2026-05-22 - Keepa Public Product Research`
- Learning: price history, alerts, and product identity normalization are the useful patterns; browser extension, scraping, API dependency, and alert automation are explicitly not promoted yet.
- Confidence: verified for public Keepa claims, inferred for architecture.

## 2026-05-22 - Manual Beer Price Run 001

- Work performed: first manual observation-format run for beer products across public Mexican ecommerce pages.
- Durable outputs:
  - `docs/experiments/manual-price-runbook-001.md`
  - `knowledge/raw/price-checks/observation-format.md`
  - `knowledge/raw/price-checks/run-2026-05-22-cervezas-001/`
  - source entry `2026-05-22 - Manual Beer Price Run 001`
- Learning: the manual format is useful but needs explicit treatment of package equivalence, membership gates, shipping, location, and availability.
- Confidence: experimental.

## 2026-05-25 - Hot Sale Bank-Promo Decision Run

- Work performed: compared high-ticket iPhone purchase routes using store prices, bank promotions, payment rails, checkout/user evidence, and user constraints.
- Durable outputs:
  - `knowledge/processed/insights/hot-sale-iphone-bank-promos-manual-run-2026-05-25.md`
  - `knowledge/processed/summaries/hot-sale-2026-promos-bancarias-2026-05-25.md`
  - `knowledge/processed/summaries/iphone17-hot-sale-bank-offer-2026-05-25.md`
  - raw evidence under `knowledge/raw/promo-checks/run-2026-05-25-hot-sale-bancos-001/`
  - raw product runs under `knowledge/raw/price-checks/run-2026-05-25-*`
- Learning: bank promotions must be modeled as route-specific rules, not simple discounts. Payment rail, MSI, registration, caps, coupons, merchant eligibility, and statement-credit timing can invert the recommendation.
- Confidence: experimental; some user-provided checkout/terms evidence is stronger than secondary deal posts, but official terms and final checkout remain required before purchase.

## 2026-05-25 - Apple TV Low-Ticket Threshold Check

- Work performed: checked Apple TV 4K on Amazon against Hot Sale bank-route thresholds.
- Durable outputs:
  - `knowledge/raw/price-checks/run-2026-05-25-apple-tv-amazon-001/README.md`
  - `knowledge/processed/summaries/apple-tv-amazon-threshold-2026-05-25.md`
  - source entry `2026-05-25 - Apple TV Amazon Hot Sale Bank Route Check 001`
- Learning: below-minimum purchases should not chase bank bonuses with filler items unless the extra basket items were already planned. Simple MSI or one-payment can be the best practical route.
- Confidence: experimental.

## 2026-05-26 - Sam's Club Bank Routes

- Work performed: compared Sam's Club Hot Sale routes across BBVA, Banamex, HSBC, Amex, INVEX/Cashi, and PayPal-style options.
- Durable outputs:
  - `knowledge/raw/promo-checks/run-2026-05-26-sams-club-bank-routes-001/README.md`
  - `knowledge/processed/summaries/sams-club-bank-routes-2026-05-26.md`
  - source entry `2026-05-26 - Sam's Club Bank Routes Hot Sale Check 001`
- Learning: the strongest Sam's route depends heavily on basket size, online vs physical channel, card segment, registration, and whether rewards are cash or Cashi wallet value.
- Confidence: experimental.

## 2026-05-26 - Sam's + Costco Offer Sweep 001

- Work performed: first visible-discount sweep across Sam's Club and Costco to identify products worth tracking.
- Durable outputs:
  - `knowledge/raw/price-checks/run-2026-05-26-sams-costco-ofertas-001/`
  - `knowledge/projects/radar-de-ofertas/offer-watchlist.md`
  - `knowledge/processed/summaries/sams-costco-offer-sweep-2026-05-26.md`
  - source entry `2026-05-26 - Sam's + Costco Offer Sweep 001`
- Learning: visible savings plus review/shipping signals can identify follow-up candidates, but "worth it" requires cross-store or historical validation. Costco exposed stronger first-pass signals than Sam's in this sweep.
- Confidence: experimental.

## Current Non-Promotion Decision

- No skill, plugin, scraper, alert, recurring monitor, or automation has been promoted.
- Best next human/agent artifact candidate: a manual bank-promotion comparison runbook, after one more high-ticket validation pass or official-terms review.
- Best next evidence task: recheck watchlist candidates against exact product pages, competitor prices, membership/shipping assumptions, and same-SKU comparability.
