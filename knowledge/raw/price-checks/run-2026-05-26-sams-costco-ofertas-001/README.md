# Sam's + Costco Offer Sweep 001

- Checked at: 2026-05-26T11:04:19-06:00
- Checked by: codex-manual-browser
- Related candidate: Comparador Manual De Precios De Bebidas En Mexico / general manual price comparison workflow
- Stores: Sam's Club Mexico; Costco Mexico
- Goal: identify products with explicit visible discount signals worth tracking, not final purchase recommendations.
- Raw structured evidence: `observations.csv`

## Sources Checked

- Sam's Club Mexico, Promociones Linea Blanca: `https://www.sams.com.mx/content/promociones-especiales/1030057`
- Costco Mexico homepage / Hot Sale product rail: `https://www.costco.com.mx/`

## Validation Performed

- Opened both stores in the Codex in-app browser.
- Cross-checked Sam's official page through web text extraction after the in-app browser later showed a temporary blocked URL on reload.
- Captured visible current price, previous price or savings when exposed, shipping/fulfillment text when exposed, and review signals when visible.
- Filtered out rows where the only visible offer signal was MSI and no previous price or savings was shown.

## Interpretation Rules Used

- `candidate_to_track`: visible discount is meaningful, but more evidence is required before recommending purchase.
- `strong_signal`: discount is explicit and review/availability/shipping evidence is reasonably useful.
- `watch_with_caution`: discount exists, but rating count is low, rating is weak, shipping is restricted, or product comparability is unclear.
- `not_a_deal_yet`: MSI or category placement only; no explicit savings captured.

## Key Findings

- Costco provided stronger first-pass tracking candidates because the page exposed savings, shipping inclusion, and ratings on multiple products.
- Sam's Linea Blanca exposed large discounts, but several products had low or missing review counts; these should be compared against Costco, Amazon, Liverpool, Walmart or manufacturer pricing before buying.
- Current evidence is insufficient to claim "worth it" in the strict sense. The next validation step is cross-store price comparison or price-history evidence for each candidate.

## Gaps

- No checkout validation.
- No postal code or account-specific location was entered.
- Membership requirements were assumed relevant for Sam's and Costco but not tested.
- Product links from Sam's were available in the official page extraction, but individual product pages were not opened in this run.
- Costco dynamic browser extraction showed sale price plus savings; static text extraction also exposed some pre-discount prices in nearby rails, so final checkout/product-page validation is required before purchase.
