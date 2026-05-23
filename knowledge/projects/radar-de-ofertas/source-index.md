# Source Index

Registry for evidence used by `radar-de-ofertas`.

Do not treat this file as raw evidence. Use it as an index pointing to URLs, timestamps, screenshots, exports, or notes stored elsewhere.

## Source Entry Template

```md
## <YYYY-MM-DD> - <Short Run Name>

- Source type: price-check | screenshot | export | notes | command-output | other
- Related candidate:
- Checked at:
- Checked by:
- Store:
- Product:
- URL:
- Raw evidence location:
- Visible price:
- Package size:
- Availability:
- Membership requirement:
- Shipping included:
- Coupon/promotion assumptions:
- Location assumptions:
- Confidence: verified | inferred | experimental | unverified
- Notes:
```

## 2026-05-22 - Chat Price Comparison Seed

- Source type: notes
- Related candidate: Comparador Manual De Precios De Bebidas En Mexico
- Checked at: 2026-05-22, exact time not persisted
- Checked by: Codex-assisted manual research in chat
- Store: Walmart, Amazon Mexico, Sam's Club, Costco
- Product: Licor 43 700 ml; Chivas Regal 12 anos 750 ml; Smirnoff No. 21 1 L; Indio 12 botellas 355 ml; Corona Extra 24 latas 355 ml; Marques del Valle 6 x 750 ml; Cune Rioja Crianza 750 ml
- URL: multiple URLs were included in the chat artifact; each must be revalidated before being treated as current evidence.
- Raw evidence location: chat artifact only; not yet persisted as raw evidence
- Visible price: multiple prices captured in chat; not yet normalized in source index
- Package size: mixed
- Availability: partially observed; not fully validated
- Membership requirement: relevant for Sam's Club and Costco; not fully normalized
- Shipping included: excluded in the chat analysis
- Coupon/promotion assumptions: bank coupons excluded in the chat analysis
- Location assumptions: Mexico; postal code not recorded
- Confidence: experimental
- Notes: Seed evidence is useful for backlog and process design, but should not be reused as current price evidence without a fresh check.

## 2026-05-22 - Manual Beer Price Run 001

- Source type: price-check | notes
- Related candidate: Comparador Manual De Precios De Bebidas En Mexico
- Checked at: 2026-05-22T23:24:30-06:00 to 2026-05-22T23:28:40-06:00
- Checked by: codex-manual
- Store: Amazon Mexico; Palacio de Hierro; Costco Mexico; Sam's Club Mexico
- Product: Corona Extra 24 x 355 ml botellas; Modelo Especial 24 x 355 ml latas; Corona Light 24 x 355 ml latas; Tecate Light 24 x 355 ml latas; Pacifico Suave 24 x 355 ml latas; Corona Cero 24 x 355 ml latas
- URL: mixed; see raw evidence notes
- Raw evidence location: `knowledge/raw/price-checks/run-2026-05-22-cervezas-001/`
- Visible price: mixed; see `observations.csv`
- Package size: 24 x 355 ml for attempted canonical products
- Availability: mixed; Sam's observed direct product pages were out of stock; Amazon observed direct product pages were in stock; other rows unknown
- Membership requirement: Sam's Club and Costco treated as required or gated; Amazon and Palacio treated as none unless evidence changes
- Shipping included: verified only where Amazon visibly showed free delivery; otherwise unknown
- Coupon/promotion assumptions: excluded
- Location assumptions: CDMX requested, but no postal code entered; browser defaults were not treated as CDMX evidence
- Confidence: experimental
- Notes: First manual validation run for the observation format. No screenshots or exports captured; evidence notes preserve checked pages, gaps, inferences, and comparability risks.
