# Keepa Analysis - 2026-05-22

## Status

- Confidence: verified for public product claims; inferred for internal architecture.
- Checked at: 2026-05-22 22:57:40 CST.
- Related spec: `docs/specs/keepa-like-radar-de-ofertas/PRD.md`

## What Keepa Does

Verified public claims:
- Keepa tracks Amazon products and provides price history charts plus price drop alerts.
- The Chrome extension embeds price history charts directly on supported Amazon product pages.
- The extension supports price drop and availability alerts, including Amazon Mexico.
- The Firefox listing describes Amazon and Marketplace price histories, price watches from the product page, and use without an account.
- Keepa offers API tooling; the official Java framework shows product requests, price history analysis and current price extraction from product CSV history.

## How Keepa Appears To Work

Inferred architecture:
- Product identity is centered on Amazon product identifiers such as ASINs.
- Keepa stores time-series observations for price, availability and offer-related data.
- Browser extensions act as a product-page UI layer: they detect Amazon pages, request Keepa data and inject charts/watch controls.
- Alerts likely compare new observations against user watch thresholds and notify through configured channels.
- API access supports programmatic retrieval of product history and analytics, but introduces account, key, token, cost and lock-in considerations.

## What To Reuse For Radar De Ofertas

Reusable product pattern:
- Price history matters more than current price alone.
- A product page or report should show historical context, not just a recommendation.
- Alerts should be driven by explicit thresholds.
- International or multi-source comparison only works after product identity is normalized.
- Evidence and uncertainty must be visible.

Do not copy yet:
- Browser extension.
- Automated scraping.
- Recurring alerts.
- API integration.
- Seller analytics.

## Mexico-First Adaptation

Radar de Ofertas should adapt the value pattern to Mexican ecommerce:
- multi-store comparison;
- price per unit;
- membership and shipping caveats;
- location assumptions;
- product/package equivalence;
- manual evidence before automation.

## Sources

- Keepa homepage: `https://keepa.com/`
- Chrome Web Store listing: `https://chromewebstore.google.com/detail/keepa-amazon-price-tracke/neebplgakaahbhdphmkckjjcegoiijjo`
- Mozilla Add-ons listing: `https://addons.mozilla.org/en-US/firefox/addon/keepa/`
- Keepa API Java Framework: `https://github.com/keepacom/api_backend`
- Python Keepa client docs, secondary source: `https://keepaapi.readthedocs.io/`
