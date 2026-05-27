# Sam's + Costco offer sweep summary

- Checked at: 2026-05-26T11:04:19-06:00
- Raw evidence: `knowledge/raw/price-checks/run-2026-05-26-sams-costco-ofertas-001/`
- Watchlist: `knowledge/projects/radar-de-ofertas/offer-watchlist.md`
- Source index entry: `2026-05-26 - Sam's + Costco Offer Sweep 001`
- Confidence: experimental

## Purpose

Identify products with visible discount signals worth rechecking. This was not a final purchase recommendation run.

## Strongest First-Pass Signals

- Costco OmniBreeze tower fan: modest discount, strong review count.
- Costco GE gas laundry center: large savings and enough reviews, but rating needs review-content validation.
- Costco Tequila 1800 Anejo Cristalino 700 ml: beverage-category candidate with explicit savings.
- Costco Apple AirPods Pro 3: clean discount signal, exact model must be verified.
- Costco Hamilton Beach Front-Fill coffee maker: small-ticket candidate with visible savings and reviews.

## Main Learning

Costco exposed richer first-pass evidence in this sweep: savings, shipping inclusion, product pages, and review signals. Sam's exposed large line-price discounts, especially in appliances, but several candidates had low or missing review confidence.

## Recommendation Boundary

Items in the watchlist are not `worth it` yet. Before recommending, require at least one of:

- same-SKU competitor comparison;
- price history or repeated observation;
- product-page and checkout validation;
- category-specific threshold and review-quality check.

## Validation Needed

- Recheck product pages for each strong signal.
- Normalize membership and shipping assumptions.
- Compare exact SKUs against Amazon, Liverpool, Walmart, Costco, Sam's, or manufacturer pricing.
- Decide category thresholds for discount percentage, absolute savings, and review count.
