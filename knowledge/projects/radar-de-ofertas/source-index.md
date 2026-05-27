# Source Index

Registry for evidence used by `radar-de-ofertas`.

Do not treat this file as raw evidence. Use it as an index pointing to URLs, timestamps, screenshots, exports, or notes stored elsewhere.

## Source Entry Template

```md
## <YYYY-MM-DD> - <Short Run Name>

- Source type: price-check | promo-check | screenshot | export | notes | command-output | other
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

## 2026-05-27 - Banorte Hot Sale Official Promo Check 001

- Source type: promo-check | notes
- Related candidate: Comparador Manual De Promociones Bancarias Hot Sale / Modelo De Rutas Y Promociones Bancarias
- Checked at: 2026-05-27T13:21:49-06:00
- Checked by: codex-web-research
- Store: Banorte
- Product: Banorte Hot Sale 2026 public official promotions
- URL: `https://www.banorte.com/Personal/Promociones-Hot-Sale.html`; `https://www.banorte.com/Personal/Tarjeta-Favorita.html`; `https://www.banorte.com/Personal/Promociones-Hot-Sale/Con-Banorte-sales-con-ventaja-Pagare.html`; `https://www.banorte.com/Personal/Promociones-Hot-Sale/Apartados-y-Ahorro.html`; `https://www.banorte.com/Personal/Promociones-Hot-Sale/CDN.html`; `https://www.banorte.com/Personal/Promociones-Hot-Sale/Credito-Hipotecario.html`; `https://www.banorte.com/Personal/Promociones-Hot-Sale/Autoestrene.html`; `https://www.banorte.com/Personal/Promociones-Hot-Sale/Seguros.html`; `https://www.banorte.com/Personal/Promociones-Hot-Sale/Cuenta-PyME.html`; `https://www.banorte.com/Personal/Promociones-Hot-Sale/TPV.html`; `https://www.banorte.com/Personal/Promociones-Hot-Sale/Disfruta-los-beneficios-de-un-Credito-PyME-en-linea.html`
- Raw evidence location: `knowledge/raw/promo-checks/run-2026-05-27-banorte-hot-sale-official-001/README.md`
- Visible price: not applicable
- Package size: not applicable
- Availability: official public Banorte Hot Sale pages visible via web research; no login or app access used
- Membership requirement: not applicable; some offers require Banorte account, card, credit approval, business account, or product eligibility
- Shipping included: not applicable
- Coupon/promotion assumptions: No ecommerce checkout discount assumed. Public card pages route to Tarjeta Favorita; exact card cashback terms remain unverified in this run.
- Location assumptions: Mexico; no personal account, card, or location data used
- Confidence: verified
- Notes: Use as official-source grounding for Banorte Hot Sale 2026 taxonomy and public product-offer terms. Do not use alone to calculate Banorte card cashback for a purchase route.

## 2026-05-27 - Amazon Mexico Bank Routes Hot Sale Check 001

- Source type: promo-check | notes
- Related candidate: Promotions and bank-offer comparison workflow
- Checked at: 2026-05-27T13:16:17-06:00
- Checked by: codex-web-research
- Store: Amazon Mexico
- Product: General Amazon Mexico Hot Sale basket, no single SKU checked
- URL: `https://www.aboutamazon.mx/noticias/tienda/amazon-mexico-llega-a-hot-sale-2026-con-miles-de-ofertas-entrega-el-mismo-dia-y-opciones-de-pago-para-todos`; `https://www.scotiabank.com.mx/promociones/hotsale`; `https://www.hsbc.com.mx/hot-sale/`; `https://www.bbva.mx/hot-sale.html`; `https://www.amazon.com.mx/b?node=120274022011`; `https://www.banamex.com/hotsale/index.html?categoria=Amazon`; `https://www.santander.com.mx/hot-sale/index.html`; `https://www.santander.com.mx/hot-sale/assets-2026/pdf/TyC-Hot-Sale-Amazon.pdf`; `https://www.amazon.com.mx/b?node=121720336011`
- Raw evidence location: `knowledge/raw/promo-checks/run-2026-05-27-amazon-mx-bank-routes-001/README.md`
- Visible price: not applicable
- Package size: not applicable
- Availability: official Hot Sale promo pages visible in web research; Amazon product checkout not performed
- Membership requirement: not applicable
- Shipping included: not applicable
- Coupon/promotion assumptions: Recommendations assume coupon accepted at checkout, registration completed before purchase, eligible card/product/payment term, and cashback/bonus budget not exhausted.
- Location assumptions: Mexico; no postal code or account login used
- Confidence: experimental
- Notes: Current snapshot favored Scotiabank for strongest immediate Amazon coupon and HSBC Premier/ONE for large eligible Amazon Mexico MSI baskets. User-provided Amazon Banorte URL later verified Banorte Amazon coupon `BANORTEHS26` and 15% one-payment TDC Digital bonus terms. Amazon BBVA URL verified `BBVAHS26` coupon plus automatic 16% bonus at BBVA 6/9 or 12/15 MSI thresholds. Verify checkout before purchase.

## 2026-05-27 - Amazon Whisky Cart Bank Route Check 001

- Source type: price-check | screenshot | notes
- Related candidate: Promotions and bank-offer comparison workflow
- Checked at: 2026-05-27T13:25:18-06:00
- Checked by: user screenshot + codex recommendation
- Store: Amazon Mexico
- Product: Johnnie Walker Black Label 1 L x1; Johnnie Walker Red Label 1 L x10
- URL: user-provided Amazon cart screenshot, no product URL captured
- Raw evidence location: `knowledge/raw/price-checks/run-2026-05-27-amazon-whisky-cart-bank-route-001/README.md`; screenshot at `/Users/vladimir.saldivar/Desktop/Screenshot 2026-05-27 at 13.24.10.png`
- Visible price: $3,871.80 MXN subtotal for 11 products
- Package size: 1 L bottles
- Availability: visible as available
- Membership requirement: none observed
- Shipping included: visible free delivery on screenshot items
- Coupon/promotion assumptions: Banorte excluded by user. Recommendation assumes checkout confirms coupon/card/category eligibility; alcohol category exclusions not fully validated.
- Location assumptions: Amazon screenshot shows delivery to Ciudad de... 06240; no location change performed
- Confidence: experimental
- Notes: At this subtotal, delayed cashback/bonification routes from BBVA, Banamex, HSBC, AMEX and Scotiabank mostly do not meet minimums. Coupon routes are more relevant unless the user adds planned eligible items to cross BBVA $5,000.

## 2026-05-27 - Amazon BBVA 5000 Cart Route Check 001

- Source type: price-check | screenshot | notes
- Related candidate: Promotions and bank-offer comparison workflow
- Checked at: 2026-05-27T13:31:43-06:00
- Checked by: user screenshot + codex recommendation
- Store: Amazon Mexico
- Product: Heineken / Dos Equis Lager 12 x 355 ml x5; Gran Malo Jamaica 750 ml x3; Johnnie Walker Red Label 1 L x10
- URL: user-provided Amazon cart screenshot, no product URL captured
- Raw evidence location: `knowledge/raw/price-checks/run-2026-05-27-amazon-bbva-5000-cart-001/README.md`; screenshot at `/Users/vladimir.saldivar/Desktop/Screenshot 2026-05-27 at 13.31.17.png`
- Visible price: $5,002.80 MXN subtotal for 18 products
- Package size: mixed beverage/alcohol items
- Availability: visible as available
- Membership requirement: none observed
- Shipping included: visible free delivery on screenshot items
- Coupon/promotion assumptions: Recommendation assumes BBVA Amazon Hot Sale terms previously captured: $5,000 minimum for 6/9 MSI and $7,500 minimum for 12/15 MSI. Final eligibility must be confirmed in checkout.
- Location assumptions: Amazon screenshot shows delivery to Ciudad de... 06240; no location change performed
- Confidence: experimental
- Notes: Best BBVA plazo for this cart is 6 or 9 MSI. The cart is too low for 12/15 MSI bonus threshold and too close to $5,000 to tolerate split charges or item removals. After checking Amazon's BBVA page, a stronger route is to lift the eligible basket to at least $5,500 before applying `BBVAHS26`, so the $500 coupon does not likely drop the charged amount below the $5,000 bonus threshold.

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

## 2026-05-22 - Keepa Public Product Research

- Source type: notes
- Related candidate: Keepa-Like Radar De Ofertas Para Mexico
- Checked at: 2026-05-22 22:57:40 CST
- Checked by: Codex web research
- Store: Keepa / browser extension stores / GitHub
- Product: Keepa Amazon Price Tracker
- URL: `https://keepa.com/`; `https://chromewebstore.google.com/detail/keepa-amazon-price-tracke/neebplgakaahbhdphmkckjjcegoiijjo`; `https://addons.mozilla.org/en-US/firefox/addon/keepa/`; `https://github.com/keepacom/api_backend`; `https://keepaapi.readthedocs.io/`
- Raw evidence location: not persisted as raw local capture; processed notes in `knowledge/processed/summaries/keepa-analysis-2026-05-22.md` and source URLs listed above.
- Visible price: not applicable
- Package size: not applicable
- Availability: public pages accessible at research time
- Membership requirement: not applicable
- Shipping included: not applicable
- Coupon/promotion assumptions: not applicable
- Location assumptions: Mexico-first adaptation is inferred for this project; Keepa public pages specifically mention Amazon `.mx` support.
- Confidence: verified
- Notes: Use this entry for product-pattern evidence only. It does not prove Keepa internal architecture beyond public descriptions and API framework examples.

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

## 2026-05-25 - Hot Sale 2026 Promociones Bancarias 001

- Source type: notes
- Related candidate: Promotions and bank-offer comparison workflow
- Checked at: 2026-05-25T08:00:53-06:00
- Checked by: codex-manual-browser
- Store: Promodescuentos / multiple banks and payment methods
- Product: Hot Sale 2026 bank and payment promotions
- URL: `https://www.promodescuentos.com/ofertas/hot-sale-2026-guia-completa-de-ofertas-bancarias-1160717`
- Raw evidence location: `knowledge/raw/promo-checks/run-2026-05-25-hot-sale-bancos-001/README.md`
- Visible price: not applicable
- Package size: not applicable
- Availability: Article visible in Codex in-app browser; event end observed as 2026-06-02 23:59
- Membership requirement: varies by bank/card/customer segment; see raw notes
- Shipping included: not applicable
- Coupon/promotion assumptions: Promodescuentos article treated as secondary evidence; official bank terms were not individually verified in this run
- Location assumptions: Mexico; no personal account, card, or location data used
- Confidence: experimental
- Notes: Use this for promotion-analysis evidence only. Before recommending a purchase, verify the selected bank's official terms, registration deadline, eligible merchants, caps, exclusions, and stacking behavior.

## 2026-05-25 - iPhone 17 Hot Sale Bank Offer Check 001

- Source type: price-check | notes
- Related candidate: Promotions and bank-offer comparison workflow
- Checked at: 2026-05-25T08:14:55-06:00
- Checked by: codex-manual-browser
- Store: El Palacio de Hierro; iShop Mixup; MacStore; Costco Mexico; Promodescuentos; BBVA; Banamex; American Express; Banorte secondary summaries
- Product: iPhone 17 256 GB
- URL: `https://www.elpalaciodehierro.com/apple-iphone-17-256-gb-salvia-45003893.html`; `https://www.ishopmixup.com/iphone-17/p`; `https://www.macstoreonline.com.mx/productos/iphone749`; `https://www.costco.com.mx/Electronicos/Apple/iPhone/Apple-iPhone-17-256GB-Azul-Neblina/p/696412`; `https://www.bbva.mx/hot-sale.html`; `https://www.banamex.com/hotsale/index.html`; `https://www.americanexpress.com/es-mx/beneficios/promociones/hot-sale.html`
- Raw evidence location: `knowledge/raw/price-checks/run-2026-05-25-iphone17-hot-sale-001/README.md`
- Visible price: $19,599.02 at El Palacio de Hierro; $19,999 at iShop/MacStore; $19,899 at Costco
- Package size: iPhone 17 256 GB
- Availability: Palacio and iShop pages visible; Palacio showed Disponible; Costco page visible; MacStore page visible but selected variant data was partially obscured in DOM
- Membership requirement: Costco likely membership-gated; not checked
- Shipping included: Palacio free over $399; iShop page mentions shipping rules; Costco includes shipping
- Coupon/promotion assumptions: Walmart Mexico and Mercado Libre excluded; bank-promo calculations assume eligible merchant, valid registration/activation, and no order split
- Location assumptions: Mexico; no postal code entered; no personal account or card data used
- Confidence: experimental
- Notes: Recommendation favored Banamex for phone-only purchase and Banorte for a $20,000+ basket. Official Banorte 2026 TyC still needs direct validation before purchase.

## 2026-05-25 - Sonos Sub Mini Amazon Bank Promo Check 001

- Source type: price-check | notes
- Related candidate: Promotions and bank-offer comparison workflow
- Checked at: 2026-05-25T08:53:25-06:00
- Checked by: codex-manual-browser
- Store: Amazon Mexico
- Product: Sonos Sub Mini, Subwoofer Inalambrico - Blanco
- URL: `https://www.amazon.com.mx/Sonos-Subwoofer-Inal%C3%A1mbrico-Intensifica-Sonido/dp/B0BKNZRW52?ref_=ast_sto_dp&th=1`
- Raw evidence location: `knowledge/raw/price-checks/run-2026-05-25-sonos-sub-mini-amazon-001/README.md`
- Visible price: $7,198.00
- Package size: one Sonos Sub Mini
- Availability: visible as Disponible
- Membership requirement: none observed
- Shipping included: Amazon showed free delivery
- Coupon/promotion assumptions: Amazon Hot Sale coupon codes from Promodescuentos treated as secondary evidence; calculations assume coupon accepted and bank bonus applies after registration
- Location assumptions: Amazon page showed delivery to Ecatepec 55067; no location change performed
- Confidence: experimental
- Notes: Product was visibly sold/fulfilled by Amazon Mexico, which is important for Amazon bank-promo eligibility. Final price must be confirmed in checkout and bank TyC.

## 2026-05-25 - iPhone 17 Best Bank Promo Refresh 001

- Source type: price-check | notes
- Related candidate: Promotions and bank-offer comparison workflow
- Checked at: 2026-05-25T09:32:58-06:00
- Checked by: codex-manual-browser
- Store: Promodescuentos; Amazon Mexico; El Palacio de Hierro; MacStore; Liverpool; Costco; Office Depot; Elektra
- Product: iPhone 17 256 GB; iPhone 17 Pro Max 256 GB
- URL: `https://www.promodescuentos.com/grupo/iphone-17`; `https://www.promodescuentos.com/search?q=iphone%2017%20pro%20max`; `https://www.elpalaciodehierro.com/apple-iphone-17-pro-max-256-gb-naranja-45003924.html`; `https://www.elpalaciodehierro.com/categorias/iphone-17/`
- Raw evidence location: `knowledge/raw/price-checks/run-2026-05-25-iphone17-best-bank-refresh-001/README.md`
- Visible price: iPhone 17 best active Promodescuentos visible $13,349 with Santander/Amazon; iPhone 17 Pro Max best visible $21,099 MacStore Banorte with title claiming $19,515 under activation TJF
- Package size: 256 GB
- Availability: Promodescuentos listings visible; store checkout availability not fully validated
- Membership requirement: Costco likely requires membership; not validated
- Shipping included: mixed; see individual store checkout before purchase
- Coupon/promotion assumptions: Calculations assume coupon accepted, bank registration complete, eligible merchant/product, and no split charges
- Location assumptions: Mexico; no checkout or account login performed
- Confidence: experimental
- Notes: Use as a current ranking snapshot only. User later provided Banorte terms clarifying that the main Banorte one-payment bonus excludes MSI, PayPal, and Mercado Pago; Banorte scenarios must use TDC Digital Banorte at one payment in participating merchants.

## 2026-05-25 - Costco Sam's PayPal iPhone 17 Hot Sale Check 001

- Source type: price-check | screenshot | notes
- Related candidate: Promotions and bank-offer comparison workflow
- Checked at: 2026-05-25T10:30:00-06:00
- Checked by: codex-manual-browser + user-provided checkout screenshots/terms
- Store: Costco Mexico; Sam's Club Mexico; PayPal Mexico
- Product: iPhone 17 256 GB; iPhone 17 Pro Max 256 GB
- URL: `https://www.costco.com.mx/content/cat-tdc`; `https://www.paypal.com/mx/webapps/mpp/shop/daily-offers`; `https://www.sams.com.mx/ayuda/articulo/promociones-bancarias/0089f183dae243c0a090ef2a93d96ce7`
- Raw evidence location: `knowledge/raw/price-checks/run-2026-05-25-costco-sams-iphone17-001/README.md`
- Visible price: Costco user checkout showed iPhone 17 Pro Max basket subtotal $30,899, coupon `VS123` -$7,500, one-payment total $23,399; Sam's search showed iPhone 17 256 GB around $19,742.88-$20,457.96.
- Package size: 256 GB
- Availability: Costco checkout screenshot showed order flow; Sam's iPhone 17 results visible in manual search; iPhone 17 Pro Max not found in observed Sam's search.
- Membership requirement: Costco and Sam's membership likely required; not independently validated in this run.
- Shipping included: Costco/Sam's shipping details not normalized in this run.
- Coupon/promotion assumptions: Costco `VS123` treated as direct Costco TDC Banamex coupon; PayPal/Banorte MSI treated as separate route from Banorte one-payment tier bonus; Sam's bank offers treated as MSI/exclusive-price evidence only.
- Location assumptions: Mexico; no postal code or personal account data changed.
- Confidence: experimental
- Notes: Do not combine Banorte one-payment bonus with PayPal/MSI. Do not assume Costco TDC Banamex coupons stack with PayPal. Sam's evidence did not produce the best current iPhone recommendation.

## 2026-05-25 - Apple TV Amazon Hot Sale Bank Route Check 001

- Source type: price-check | notes
- Related candidate: Comparador Manual De Promociones Bancarias Hot Sale
- Checked at: 2026-05-25T11:15:00-06:00
- Checked by: codex-manual-browser
- Store: Amazon Mexico
- Product: Apple TV 4K Wi-Fi + Ethernet 128 GB, tercera generacion
- URL: `https://www.amazon.com.mx/Apple-Wi%E2%80%91Fi-Almacenamiento-Tercera-generaci%C3%B3n/dp/B0BJN3WNR2`
- Raw evidence location: `knowledge/raw/price-checks/run-2026-05-25-apple-tv-amazon-001/README.md`
- Visible price: $3,699.00
- Package size: one Apple TV 4K 128 GB
- Availability: visible as "Solo hay 2 disponible(s)"
- Membership requirement: none observed
- Shipping included: Amazon page showed free delivery to the browser's current delivery location
- Coupon/promotion assumptions: BBVA 15 MSI visible on product page; bank cashback routes treated as not useful for standalone purchase because product price is below captured Hot Sale minimum thresholds.
- Location assumptions: Browser showed delivery to Ecatepec 55067; no location change performed.
- Confidence: experimental
- Notes: Use as evidence for a low-ticket threshold lesson: below-minimum products should prefer simple MSI or cash payment unless the user already has planned basket items to cross a promotion threshold.

## 2026-05-26 - Sam's Club Bank Routes Hot Sale Check 001

- Source type: promo-check | notes
- Related candidate: Comparador Manual De Promociones Bancarias Hot Sale
- Checked at: 2026-05-26T00:00:00-06:00
- Checked by: codex-web-research
- Store: Sam's Club Mexico
- Product: Sam's Club Hot Sale purchase routes
- URL: `https://www.sams.com.mx/content/meses-sin-intereses/promociones-bancarias/230005_1410042`; `https://www.bbva.mx/hot-sale.html`; `https://www.banamex.com/hotsale/index.html`; `https://www.hsbc.com.mx/hot-sale/`; `https://www.americanexpress.com/es-mx/beneficios/promociones/hot-sale.samclub.html`; `https://promociones.invextarjetas.com.mx/guia-de-uso-invex-sams/`; `https://cashi.com.mx/samsclub`
- Raw evidence location: `knowledge/raw/promo-checks/run-2026-05-26-sams-club-bank-routes-001/README.md`
- Visible price: not applicable
- Package size: not applicable
- Availability: pages visible via web research
- Membership requirement: Sam's Club membership required for purchases; Sam's Club INVEX guide also notes membership is required.
- Shipping included: not normalized in this run.
- Coupon/promotion assumptions: BBVA, Banamex, HSBC and Amex routes depend on checkout/product eligibility and bank terms. Sam's Club INVEX rewards are Cashi wallet value, not generic cash.
- Location assumptions: Mexico; no account login performed.
- Confidence: experimental
- Notes: Strongest route depends on basket size: small/everyday Sam's Club INVEX/Cashi; online $5,000-$9,999 BBVA; online $10,000+ Banamex; online $13,500+ HSBC if eligible; physical-store MSI Amex from $3,500.

## 2026-05-26 - Sam's + Costco Offer Sweep 001

- Source type: price-check | notes
- Related candidate: Comparador Manual De Precios De Bebidas En Mexico / general manual price comparison workflow
- Checked at: 2026-05-26T11:04:19-06:00
- Checked by: codex-manual-browser
- Store: Sam's Club Mexico; Costco Mexico
- Product: Linea blanca, appliances, beverage, electronics, furniture, personal/home products with explicit visible savings
- URL: `https://www.sams.com.mx/content/promociones-especiales/1030057`; `https://www.costco.com.mx/`
- Raw evidence location: `knowledge/raw/price-checks/run-2026-05-26-sams-costco-ofertas-001/`
- Visible price: mixed; see `observations.csv`
- Package size: mixed; see `observations.csv`
- Availability: mixed; mostly visible add/available signals, no checkout validation
- Membership requirement: Costco and Sam's membership likely required; not independently validated in checkout
- Shipping included: Costco often showed `Incluye envio`; Sam's showed Envio estandar or Club Pickup; see row-level notes
- Coupon/promotion assumptions: bank promos, MSI, and checkout coupons excluded from deal scoring
- Location assumptions: Mexico; no postal code entered or changed
- Confidence: experimental
- Notes: First sweep focused on visible discount quality signals for products worth tracking. Not enough evidence to make final purchase recommendations without cross-store or price-history validation.

## 2026-05-27 - Sam's BBVA vs PayPal Price-Base Check 001

- Source type: promo-check | notes
- Related candidate: Comparador Manual De Promociones Bancarias Hot Sale
- Checked at: 2026-05-27T10:46:00-06:00
- Checked by: codex-web-research + user-provided domain observation
- Store: Sam's Club Mexico; BBVA Mexico; PayPal Mexico
- Product: Sam's Club Hot Sale purchase routes where Sam's may expose contado vs bank/MSI pricing
- URL: `https://www.sams.com.mx/content/hot-sale/90001`; `https://www.sams.com.mx/content/meses-sin-intereses/promociones-bancarias/230005_1410042`; `https://www.bbva.mx/content/dam/public-web/mexico/documents/tycs/Terminos-y-Condiciones-HOT-SALE-2026.pdf`
- Raw evidence location: `knowledge/raw/promo-checks/run-2026-05-27-sams-bbva-paypal-price-base-001/README.md`
- Visible price: not captured for a specific SKU in this follow-up
- Package size: not applicable
- Availability: not checked for a specific SKU
- Membership requirement: Sam's Club membership likely required; exact checkout route not validated in this follow-up
- Shipping included: not normalized
- Coupon/promotion assumptions: PayPal + BBVA should only be modeled as eligible if PayPal checkout confirms BBVA credit card at eligible MSI. BBVA direct should use the final Sam's BBVA/MSI checkout total, not the cash-like headline price.
- Location assumptions: Mexico; no account login, postal code change or personal card data used
- Confidence: experimental
- Notes: Main reusable learning is the three-route comparison formula: contado checkout total vs BBVA direct MSI total minus expected bonus vs PayPal checkout total minus expected bonus. Needs SKU-level checkout screenshots before any final recommendation.
