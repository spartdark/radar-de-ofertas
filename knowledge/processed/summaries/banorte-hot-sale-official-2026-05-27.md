# Banorte Hot Sale 2026 official sources summary

- Date checked: 2026-05-27T13:21:49-06:00
- Raw evidence: `knowledge/raw/promo-checks/run-2026-05-27-banorte-hot-sale-official-001/README.md`
- Confidence: verified for public official Banorte pages; unverified for personalized card offers not exposed without login.

## Summary

Banorte's official Hot Sale 2026 public hub presents a broad financial-products campaign, not only a card cashback campaign. Public pages cover card promotion access via Tarjeta Favorita, Pagare Digital, Apartados y Ahorro, Credito de Nomina, Credito Hipotecario, Credito de Auto, Seguros, Credito PyME en linea, Cuenta PyME and Terminal Punto de Venta.

The most useful finding for `radar-de-ofertas` is a boundary: the public Banorte pages are enough to confirm the official campaign taxonomy and several non-card offers, but they are not enough to safely model the high-value Tarjeta de Credito Digital Banorte Hot Sale purchase route. That route still needs official Tarjeta Favorita terms or user-provided activated-offer screenshots.

## Official public offers observed

| Offer area | Public benefit observed | Key constraints observed |
|---|---|---|
| Tarjetas / Tarjeta Favorita | Hot Sale portal routes debit and credit cards to Tarjeta Favorita. | Public page describes promotion discovery/registration, but no public Hot Sale cashback table was visible without app/account context. |
| Pagare Digital | Special rate for one year. | From $5,000, 28-day term, Banorte Movil/Banco en Linea, first-time term investment condition. |
| Apartados y Ahorro | $1,000 bonus for $5,000+ Apartado or Ahorro Programado. | Keep active until 2026-07-15; bonus by 2026-08-14; limited to first 3,000; one per client. |
| Credito de Nomina | $250 MXN Amazon digital wallet value. | Eligible contracts 2026-05-25 to 2026-06-02; minimum $100,000; active at least one month; first 5,000 eligible clients. |
| Credito Hipotecario | 0% contracting-credit commission plus product rates/benefits. | Product-specific rates/CATs; requires branch/promotor process and normal credit documentation. |
| Credito de Auto | 0% contracting-credit commission and insurance coverage benefits. | Request during campaign; choose/formalize auto by 2026-06-15; subject to credit approval. |
| Seguros | 25% discount on participating Seguros Banorte and MSI with Banorte credit card. | Not cumulative with other discounts/promotions; channels and products vary. |
| Credito PyME en linea | Up to $8M MXN, 0% opening commission, up to 60 months. | Valid 2026-05-25 to 2026-06-02; subject to credit approval. |
| Cuenta PyME | No opening minimum and membership-fee benefit. | 6 months free in CDMX branches, 3 months elsewhere; extension requires active e-banking and additional product. |
| Terminal Punto de Venta | Up to 6 months commission/discount-rate bonus and up to 40% MSI surcharge bonus. | New affiliation, billing and active-product conditions; PyME/commercial scope. |

## Implications for offer comparisons

- Treat Banorte Hot Sale as multiple promotions with different objects: card checkout route, savings/investment route, loan acquisition route, insurance route and merchant-acquiring route.
- Do not mix public financial-product offers with ecommerce checkout discounts.
- Do not calculate Banorte card cashback from secondary sources when the official Tarjeta Favorita terms are missing.
- If a user wants to evaluate a specific purchase with Banorte, require: activated official offer screenshot or official terms, merchant eligibility, card type, payment rail, one-payment/MSI rule, minimum spend, cap, reward timing, and checkout total.

## Open questions

- Does Banorte publish a public PDF or landing page for the 2026 Tarjeta de Credito Digital Hot Sale cashback table, or is it only available through Tarjeta Favorita?
- What are the exact 2026 card caps, minimum spends, payment-method exclusions, registration deadline and reward timing?
- Which ecommerce merchants are official participants for Banorte card promotions, and do wallets/PayPal/Mercado Pago invalidate any route?

## Decision

Keep this as `knowledge`. It strengthens the existing bank-promotion comparison memory, but it is not sufficient to promote a Banorte Hot Sale card workflow to a doc, skill, plugin or automation.
