# Sam's Club bank routes Hot Sale summary

- Checked at: 2026-05-26T00:00:00-06:00
- Raw evidence: `knowledge/raw/promo-checks/run-2026-05-26-sams-club-bank-routes-001/README.md`
- Related follow-up: `knowledge/raw/promo-checks/run-2026-05-27-sams-bbva-paypal-price-base-001/README.md`
- Source index entry: `2026-05-26 - Sam's Club Bank Routes Hot Sale Check 001`
- Confidence: experimental

## Practical Route Map

| Basket / channel | Best observed route candidate | Why |
|---|---|---|
| Small or everyday Sam's purchase | Sam's Club INVEX + Cashi | Sam's-native value, but reward is Cashi wallet value rather than generic cash. |
| Online $5,000-$9,999 | BBVA | Lower online MSI bonus thresholds than Banamex/HSBC in captured evidence. |
| Online $10,000+ | Banamex 18 MSI | Competitive if registration, digital-card and merchant eligibility are satisfied. |
| Online $13,500+ | HSBC | Can beat others only for eligible Premier/ONE/invited segments and participating online merchant scope. |
| Physical store from $3,500 | American Express MSI | Observed as Sam's physical-store MSI route, not validated as cashback. |

## Learning

Sam's Club should not be modeled as one generic discount environment. Channel, basket size, card segment, registration, reward type, and payment rail change the route.

For products where Sam's exposes different price bases by payment route, compare `contado`, `BBVA direct at MSI`, and `PayPal + BBVA at MSI` separately. The useful formula is checkout-total based:

| Route | Compare as |
|---|---|
| Contado / cash-like | `contado checkout total` |
| BBVA direct | `BBVA/MSI checkout total - expected BBVA bonus` |
| PayPal + BBVA | `PayPal checkout total - expected BBVA bonus`, only if PayPal confirms BBVA credit card at eligible MSI |

The current working hypothesis from the 2026-05-27 chat is that PayPal may preserve Sam's cash-like price while BBVA direct may use a higher MSI price. This is not yet verified for a specific SKU with checkout screenshots.

## Validation Needed

- Confirm Sam's official terms and checkout eligibility for the exact basket.
- Separate Cashi wallet value from cash cashback.
- Verify whether PayPal, wallets, MSI, or digital-card requirements exclude a route.
- When Sam's shows two prices, capture final totals for contado, BBVA direct and PayPal + BBVA before recommending a route.
- Recheck shipping, membership and stock before purchase.
