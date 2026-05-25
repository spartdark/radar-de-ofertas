# Hot Sale iPhone bank promos manual run

- Run date: 2026-05-25
- Run type: manual research / wizard-of-oz analysis
- Domain: high-ticket ecommerce offer comparison in Mexico
- Products: iPhone 17 256 GB; iPhone 17 Pro Max 256 GB; side check Sonos Sub Mini
- Main stores/payment rails: Amazon Mexico, Costco Mexico, Sam's Club Mexico, El Palacio de Hierro, Liverpool, MacStore, iShop, Office Depot, PayPal
- Main banks/cards: Banorte, Banamex, BBVA, American Express, Santander as outside-priority benchmark
- Evidence status: experimental
- Related raw evidence:
  - `knowledge/raw/promo-checks/run-2026-05-25-hot-sale-bancos-001/README.md`
  - `knowledge/raw/price-checks/run-2026-05-25-iphone17-hot-sale-001/README.md`
  - `knowledge/raw/price-checks/run-2026-05-25-iphone17-best-bank-refresh-001/README.md`
  - `knowledge/raw/price-checks/run-2026-05-25-costco-sams-iphone17-001/README.md`
  - `knowledge/raw/price-checks/run-2026-05-25-sonos-sub-mini-amazon-001/README.md`
- Related summaries:
  - `knowledge/processed/summaries/hot-sale-2026-promos-bancarias-2026-05-25.md`
  - `knowledge/processed/summaries/iphone17-hot-sale-bank-offer-2026-05-25.md`

## Purpose

Turn a chat-based Hot Sale purchase decision into durable learning for `radar-de-ofertas`.

The manual run tested whether a future app can compare a high-ticket product across stores while accounting for coupons, statement credits, MSI, bank caps, excluded payment rails, merchant eligibility, and user preferences.

## User Goal Captured

Find the best practical route to buy an iPhone 17 or iPhone 17 Pro Max during Hot Sale 2026, prioritizing BBVA, Banorte, Banamex, American Express, El Palacio de Hierro, and later Costco/Sam's/PayPal evidence.

Constraints and preferences captured:

- Exclude Walmart Mexico and Mercado Libre.
- Prefer BBVA, Banorte, Banamex, and American Express, but allow comparison against Santander as a benchmark if it is clearly better.
- Compare both net price and financing convenience.
- Distinguish one-payment bonuses from MSI bonuses.
- Do not assume bank promos stack with wallets, PayPal, store coupons, or MSI unless terms support it.

## Manual Workflow Performed

1. Read secondary Hot Sale promotion summaries from Promodescuentos to discover candidate promos.
2. Checked product and store candidates for iPhone 17 and iPhone 17 Pro Max.
3. Compared bank mechanics:
   - percentage statement bonus;
   - fixed cashback;
   - tiered cashback;
   - direct store coupon;
   - MSI route;
   - wallet route through PayPal.
4. Incorporated user-provided terms and checkout screenshots as stronger evidence than community summaries.
5. Re-ranked recommendations after each new constraint:
   - Banorte terms excluding MSI/PayPal;
   - Costco direct coupon evidence;
   - PayPal daily offer route;
   - Banamex Amazon 18 MSI screenshot;
   - Sam's Club bank-promo page.
6. Preserved conclusions as raw evidence, processed summaries, and source-index entries.

## Key Findings

### Bank-promo mechanics are not interchangeable

The same bank can have separate offer families:

- Banorte one-payment tiered bonus at participating merchants.
- Banorte PayPal/MSI-style promo.
- Store direct coupon with a co-branded card, such as Costco + TDC Costco Banamex.

The app must model these as separate promotion objects, not as one bank-level discount.

### Payment rail eligibility is a first-class rule

User-provided Banorte terms changed the recommendation:

- main Banorte tiered bonus requires TDC Digital Banorte;
- purchase must be one payment;
- participating merchant required;
- PayPal and Mercado Pago excluded;
- MSI excluded.

This invalidates any calculation that combines Banorte's one-payment tier ladder with PayPal or MSI.

### Best offer depends on optimization objective

For iPhone 17 Pro Max:

- Best observed net-price route: Banorte one-payment at MacStore/Liverpool-style eligible merchants, subject to validation.
- Best clean immediate Costco route: Costco + TDC Costco Banamex direct coupon `VS123` at $23,399 one payment from user checkout screenshot.
- Best financing-style candidate: Costco + PayPal + Banorte MSI if the separate PayPal/Banorte terms validate, but it is not combinable with Banorte's one-payment tier bonus.

For iPhone 17:

- Best observed overall benchmark: Amazon + Santander at $13,349, outside the user's priority banks.
- Best priority-bank MSI candidate: Amazon + Banamex 18 MSI with 15% bonus, subject to registration, cap, seller, coupon, and checkout validation.
- Best priority-bank net candidate: Banorte one-payment if the basket crosses $20,000 and the added item is useful.

### Caps and thresholds create nonlinear recommendations

The app should not sort only by discount percentage.

Examples:

- BBVA 15% can lose to Banamex because the cap binds.
- Banorte can become best only when a basket crosses a tier threshold.
- Costco `VS123` is excellent at $30,000+ but does not imply a better offer below that threshold.
- A small add-on can improve net value if it triggers the next tier, but only if the add-on has real utility.

### Store coupons and bank bonuses need ordering assumptions

For any route with both coupon and bank bonus, the calculation must state whether the bank bonus applies to:

- pre-coupon subtotal;
- post-coupon paid amount;
- accumulated bank spend;
- individual transaction amount;
- daily or campaign aggregate.

If ordering is unknown, the app should show a range or require checkout validation.

## Product/App Requirements Learned

### Data model candidates

The future app likely needs these entities:

- `Product`: canonical name, model, storage, color, carrier lock status, warranty/seller flags.
- `StoreOffer`: store, URL, visible price, availability, membership requirement, shipping assumption, timestamp.
- `PaymentMethod`: bank, card type, digital/physical requirement, co-branded requirement.
- `Promotion`: type, period, registration requirement, eligible stores, payment rail rules, MSI rules, minimum spend, max benefit, tier ladder, exclusions.
- `Stack`: combination of store offer + coupon + payment method + promotion.
- `Calculation`: final estimated price, cash-flow type, confidence, assumptions, validation blockers.
- `Evidence`: URL, screenshot/note, observed timestamp, source confidence, user-provided vs browser-observed.

### UX requirements

The app should let the user choose an objective:

- lowest net price;
- best MSI;
- lowest upfront charge;
- lowest risk / most immediate discount;
- only my banks/cards;
- exclude stores or payment rails.

For each recommendation, the app should show:

- effective final price;
- upfront charge;
- expected later bonus;
- months and monthly payment if MSI;
- required activation/registration;
- cap used;
- excluded rails;
- confidence and evidence age;
- final checklist before checkout.

### Validation checklist for recommendations

Before recommending a purchase as actionable, require:

- product/store URL checked today or within accepted recency;
- seller and fulfillment validated when marketplace matters;
- exact payment mode observed in checkout;
- coupon accepted in checkout when coupon is part of the route;
- bank registration/activation completed before purchase;
- cap/minimum/tier checked against the final paid amount;
- exclusions checked for PayPal, Mercado Pago, Apple Pay, wallets, MSI, and split charges;
- screenshot or notes captured for the final cart if the purchase is high value.

## Open Questions

- How should the app represent uncertain stacking: range, warning, or block recommendation until checkout validation?
- Should user-provided screenshots be treated as higher-confidence evidence than secondary deal posts but lower than official terms?
- Should Sam's Club be excluded automatically when the user excludes Walmart Mexico, or should it be a separate toggle?
- How should the app price the value of MSI versus one-payment delayed bonus?
- Should the app recommend adding a small item to cross a bank tier, and what rules prevent low-quality basket padding?
- How should statement-credit timing and failure risk be reflected in ranking?

## Risks Observed

- Community posts can be accurate for discovery but incomplete for official terms.
- Bank promotions can share similar language while differing on caps, rails, and payment mode.
- Checkout UI may show installment options that are not actually interest-free.
- Direct store coupons may be confused with bank cashback.
- A route can look cheaper but require delayed bonus, manual activation, or post-purchase claim risk.
- Prices, stock, and coupon redemption can change during the same day.

## Reuse Decision

Keep this as `knowledge/processed/insights` and supporting raw evidence for now.

This is a strong second manual run for the project, but it should not yet become a skill, plugin, or automation. It can inform a future human/agent runbook after one more comparable high-ticket manual run or a focused validation pass on official bank terms.

## Candidate Promotion Signal

This run strengthens the case for a future reusable workflow:

`high-ticket-product + user card inventory + store exclusions + promo terms -> ranked purchase routes with evidence and checkout checklist`.

Suggested next artifact after another validation pass:

- `docs/runbooks/manual-bank-promo-comparison.md`

Do not create it yet unless explicitly requested.
