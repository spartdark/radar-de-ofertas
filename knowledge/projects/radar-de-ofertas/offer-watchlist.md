# Offer Watchlist

Products worth tracking for `radar-de-ofertas`.

This is not a buy list. A product enters this file when it has a visible discount signal and enough evidence to justify follow-up comparison. It becomes a recommendation only after cross-store or historical validation.

## Scoring Rubric

- Strong signal: explicit discount or savings, current price, source URL, timestamp, availability/shipping signal, and useful review signal.
- Candidate to track: explicit discount, but one or more validation gaps remain.
- Watch with caution: discount exists, but review count, rating, comparability, delivery, or membership assumptions make the value uncertain.
- Not a deal yet: only MSI, banner placement, or marketing copy; no explicit savings captured.

## 2026-05-26 - Sam's + Costco First Sweep

- Raw evidence: `knowledge/raw/price-checks/run-2026-05-26-sams-costco-ofertas-001/`
- Checked at: 2026-05-26T11:04:19-06:00
- Confidence: experimental

### Strong Signals To Recheck

| Store | Product | Price | Savings | Discount | Why track |
|---|---:|---:|---:|---:|---|
| Costco | OmniBreeze Ventilador de Torre con Control WiFi 5 Velocidades | $659.00 | $140.00 | 17.52% | Very strong review signal: 4.6/5 from 502 reviews. |
| Costco | GE Centro de Lavado de Gas 23kg / 23kg | $19,999.00 | $10,000.00 | 33.33% | Large discount, shipping included, 52 reviews; validate moderate 4.1 rating. |
| Costco | Tequila 1800 Anejo Cristalino 700 ml | $749.25 | $249.75 | 25.00% | Beverage category candidate with explicit savings and 37 reviews. |
| Costco | Apple AirPods Pro 3 | $4,399.00 | $1,100.00 | 20.00% | Clean discount and shipping included; verify exact model and retail baseline. |
| Costco | Hamilton Beach Cafetera Programable Front-Fill 12 Tazas | $1,199.00 | $300.00 | 20.01% | Small-ticket product with clear savings and 32 reviews. |

### Candidates To Track

| Store | Product | Price | Savings | Discount | Validation needed |
|---|---:|---:|---:|---:|---|
| Sam's | Lavadora LG Carga Frontal 20 kg WM20WV26W | $11,198.00 | $3,429.87 | 23.45% | Compare against Costco/Amazon/Liverpool; confirm delivery and product specs. |
| Sam's | Combo de Lavadora y Secadora de Gas LG 20 kg Blanco | $21,998.00 | $6,133.45 | 21.80% | Compare exact gas combo alternatives; rating is acceptable but not strong. |
| Sam's | Congelador Horizontal Hisense 18 Pies Cubicos FC18D6AWX | $11,762.45 | $5,116.01 | 30.31% | Need reviews and competitor prices. |
| Sam's | Frigobar Hisense 4.3 Pies Cubicos Negro RR43D6ABX1 | $3,367.72 | $1,534.47 | 31.30% | Compare capacity-normalized price against Costco Dace and other stores. |
| Costco | Thomasville Sofa Seccional de Tela con Otomano con Almacenamiento | $20,999.00 | $9,000.00 | 30.00% | Validate dimensions, delivery, and comparable models. |
| Costco | Dace Frigobar Coca-Cola 3.2 | $2,999.00 | $700.00 | 18.92% | Normalize capacity/brand against Sam's and Amazon. |

### Watch With Caution

| Store | Product | Price | Savings | Discount | Risk |
|---|---:|---:|---:|---:|---|
| Sam's | Vitrina Refrigerador Hisense Multi Flow 9 Pies Cubicos Azul CVC494N3AWX | $13,593.62 | $6,860.23 | 33.54% | 3/5 from 1 review. |
| Sam's | Lavadora Hisense Smart Fuzzy Carga Superior 20 kg Negra WT5i2023DB | $9,198.82 | $5,114.98 | 35.73% | 5/5 from only 1 review. |
| Sam's | Refrigerador LG 25 Pies Cubicos French Door GM25BPT | $18,340.34 | $8,255.59 | 31.04% | Only 1 visible review; big-ticket purchase needs spec and delivery validation. |

## Open Questions

- Which categories should be tracked first: despensa, bebidas, electronica, linea blanca, hogar, or high-ticket bank-promo purchases?
- Should membership cost be amortized into the effective price when the buyer is not already a member?
- What is the minimum discount threshold by category?
- Should the radar require a same-SKU cross-store check before labeling `strong_signal`?
