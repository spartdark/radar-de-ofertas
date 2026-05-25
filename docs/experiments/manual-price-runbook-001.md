# Manual Price Runbook 001

Status: draft experiment, not promoted to reusable template.

Purpose: run the first auditable manual price-check for `radar-de-ofertas` without scraping, automation, credentials, or stored personal data.

## Decision Gate

Run this experiment to decide whether the manual price-comparison process is clear enough to later promote into a validated `docs/template`.

Do not use this runbook to justify a skill, plugin, webapp, API integration, scraper, or automation yet.

## Scope

- Category: choose one narrow category before starting.
- Products: 5 to 10 products.
- Stores: 3 to 5 public Mexican ecommerce stores.
- Method: manual observation only.
- Output: observation rows, evidence notes, source-index entries, and a short run summary.

Recommended first category: beverages, because the project already has seed memory for this domain.

Recommended first stores:
- Amazon Mexico
- Walmart Mexico
- Costco Mexico
- Sam's Club Mexico

Use fewer stores if membership, availability, or location assumptions make the run hard to audit.

## Inputs

Before capture, define:

- `run_id`, for example `run-2026-05-23-beverages-001`
- category
- product list
- store list
- location assumption, without storing personal address details
- whether shipping is included, excluded, or only noted as a caveat
- whether coupons, bank promotions, and membership discounts are included or excluded

## Setup

1. Create a run folder under `knowledge/raw/price-checks/`.

   Example:

   ```txt
   knowledge/raw/price-checks/run-2026-05-23-beverages-001/
   ```

2. Create an observations file in that folder.

   Suggested file:

   ```txt
   observations.csv
   ```

3. Copy the CSV header from `knowledge/raw/price-checks/observation-format.md`.

4. Create one evidence note per product-store observation when no screenshot or raw export is available.

## Capture Steps

For each product:

1. Open the public product page for each target store.
2. Confirm the visible product name, brand, variant, and package size.
3. Decide whether it matches the canonical product.
4. Capture visible price in MXN.
5. Capture availability.
6. Capture membership requirement.
7. Capture shipping status or mark it as excluded/unknown.
8. Capture coupon and promotion assumptions.
9. Record location assumption without storing private address details.
10. Save an evidence note or screenshot reference.
11. Fill one observation row using the observation format.
12. Mark confidence honestly:
    - `verified`: direct evidence exists and required fields are complete.
    - `experimental`: direct evidence exists but this is part of the first validation run.
    - `inferred`: a field is reasoned from visible context but not directly shown.
    - `unverified`: required evidence is missing.

## Comparability Rules

Mark `not_comparable` in notes when any of these differ materially:

- brand
- variant or flavor
- bottle size, weight, or unit count
- pack quantity
- condition
- seller type when it affects price or availability
- membership requirement that changes the effective buyer pool

If products differ only by package size but are otherwise equivalent, calculate price per unit and state the assumption.

## Recommendation Rules

For the first run, avoid strong recommendations. Use conservative labels:

- `best observed in this run`
- `needs more history`
- `not comparable`
- `evidence incomplete`

Do not say `historically low` until at least three comparable observations exist for the same canonical product.

## Run Summary

After capture, create a short summary in the same run folder:

```md
# Run Summary

- Run id:
- Date:
- Category:
- Products attempted:
- Products captured:
- Stores checked:
- Observation count:
- Observations with complete required fields:
- Observations marked not comparable:
- Main blockers:
- Decisions affected:
- Candidate next step:
```

## Done Criteria

The first run is complete when:

- every observation has a timestamp, store, product, URL or explicit gap, price or explicit gap, package size, and confidence label;
- each recommendation references observation rows, not memory from chat;
- all membership, shipping, coupon, and location assumptions are visible;
- source-index entries point to the run folder or evidence notes;
- gaps and blockers are listed in the run summary.

## Stop Conditions

Stop and record the blocker if:

- a store requires login or account-specific data;
- a site requires personal address details to show price;
- products cannot be matched without guesswork;
- most prices are hidden, unavailable, or only visible through coupons;
- evidence cannot be preserved without sensitive data.

## Post-Run Decision

After the first run:

- Keep as `knowledge` if evidence is incomplete or the format is cumbersome.
- Iterate the format if key caveats are missing.
- Consider a second manual run if at least half of observations are auditable.
- Consider promotion to `docs/template` only after manual validation, preferably after two reviewed runs.
