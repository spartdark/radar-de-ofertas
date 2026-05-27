# Sam's Club BBVA vs PayPal price-base check 001

- Checked at: 2026-05-27T10:46:00-06:00
- Checked by: codex-web-research + user-provided domain observation
- Scope: Sam's Club Mexico Hot Sale purchase-route comparison for BBVA direct vs PayPal using BBVA
- Confidence: experimental

## User Observation

- Sam's Club may expose two effective price bases for a product: a lower `contado` or cash-like price and a higher bank/MSI route price.
- User reports PayPal is treated by Sam's Club as `contado` for the observed checkout route.
- The unresolved question is whether PayPal + BBVA can keep the lower Sam's price while still triggering BBVA Hot Sale MSI bonus eligibility.

## Evidence Summary

- BBVA Hot Sale 2026 terms observed in official BBVA material:
  - Online purchases at MSI with BBVA credit card can receive up to 15% bonus.
  - Minimum $5,000 for 6 or 9 MSI.
  - Minimum $7,500 for 12 to 24 MSI.
  - Maximum bonus $2,500 MXN per day/client.
  - PayPal purchases have a longer bonus-crediting window than ordinary direct merchant routes.
- Sam's Club Hot Sale / bank-route evidence from the previous run showed BBVA, PayPal and other bank/payment logos in the Sam's online promotion environment.
- Current chat analysis did not include a fresh checkout screenshot proving the exact final totals for a specific Sam's SKU.

## Practical Interpretation

For Sam's Club products with distinct cash-like and bank/MSI prices, compare three routes:

| Route | Formula |
|---|---|
| Contado / cash-like Sam's route | `sam's contado price` |
| BBVA direct at MSI | `sam's BBVA/MSI price - BBVA bonus` |
| PayPal + BBVA at MSI | `sam's PayPal/contado price - BBVA bonus`, only if PayPal checkout confirms BBVA credit card at eligible MSI |

PayPal + BBVA can be the strongest route if both conditions are true:

- Sam's keeps the lower cash-like price when PayPal is selected.
- PayPal lets the buyer select the BBVA credit card at eligible MSI inside PayPal.

BBVA direct can still win if the Sam's BBVA/MSI price uplift is smaller than the expected BBVA bonus, but the uplift must be calculated against the checkout total, not against the product page headline price.

## Validation Needed

- Capture final checkout screenshots for the same SKU and quantity under:
  - contado or one-payment route;
  - BBVA direct at eligible MSI;
  - PayPal with BBVA credit card at eligible MSI.
- Confirm the PayPal screen shows the BBVA credit card and selected MSI before purchase.
- Preserve timestamp, product URL, SKU/name, quantity, shipping, membership assumptions and final total for each route.
- After purchase, verify whether BBVA credits the bonus and record whether it follows the direct-route or PayPal delayed timeline.

## Open Questions

- Does Sam's consistently treat PayPal as contado across categories, or only for specific products?
- Does PayPal eligibility depend on card, account, product category, or merchant configuration?
- Does BBVA treat Sam's + PayPal as PayPal rail evidence or Sam's merchant evidence for bonus timing and disputes?
