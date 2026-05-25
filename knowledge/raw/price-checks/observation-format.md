# Price Observation Format

Status: draft for manual validation.

Use this format for each observed price in a manual price-check run. One row equals one store-product observation at one specific time.

Do not use an observation for a strong recommendation unless the required fields are complete or the gaps are explicitly marked.

## Required Fields

| Field | Required | Description |
|---|---:|---|
| `run_id` | yes | Stable id for the manual run, for example `run-2026-05-23-beverages-001`. |
| `observed_at` | yes | ISO-like local timestamp with timezone, for example `2026-05-23T10:30:00-06:00`. |
| `checked_by` | yes | Operator or agent that captured the observation. |
| `store` | yes | Store name, for example `Amazon Mexico`, `Walmart`, `Costco`, or `Sam's Club`. |
| `product_url` | yes | Public product URL. Mark `missing` if captured from an offline source. |
| `canonical_product_id` | yes | Project-controlled id for the comparable product, for example `licor-43-original-700ml`. |
| `visible_product_name` | yes | Product name as shown by the store. |
| `brand` | yes | Brand as observed or inferred. |
| `variant` | yes | Variant, flavor, model, edition, or `unknown`. |
| `package_size` | yes | Human-readable package size, for example `700 ml`, `12 x 355 ml`, `1 kg`. |
| `unit_quantity` | yes | Numeric quantity used for unit comparison, for example `700` or `4260`. |
| `unit` | yes | Unit used for comparison, for example `ml`, `g`, `piece`. |
| `visible_price_mxn` | yes | Visible final item price in MXN before shipping unless noted. |
| `price_per_unit_mxn` | yes | `visible_price_mxn / unit_quantity`, rounded consistently. |
| `availability` | yes | `in_stock`, `out_of_stock`, `limited`, or `unknown`. |
| `membership_requirement` | yes | `none`, `required`, or `unknown`. |
| `shipping_included` | yes | `yes`, `no`, `not_applicable`, or `unknown`. |
| `coupon_assumptions` | yes | `none`, `excluded`, `included`, or `unknown`. |
| `location_assumptions` | yes | Country, city, postal-code assumption, or `not_recorded`. |
| `evidence_location` | yes | Local path to screenshot, note, export, or raw capture. |
| `confidence` | yes | `verified`, `inferred`, `experimental`, or `unverified`. |
| `notes` | no | Gaps, caveats, mismatches, or reviewer notes. |

## CSV Header

```csv
run_id,observed_at,checked_by,store,product_url,canonical_product_id,visible_product_name,brand,variant,package_size,unit_quantity,unit,visible_price_mxn,price_per_unit_mxn,availability,membership_requirement,shipping_included,coupon_assumptions,location_assumptions,evidence_location,confidence,notes
```

## Placeholder Row

```csv
run-YYYY-MM-DD-category-001,YYYY-MM-DDTHH:MM:SS-06:00,codex-manual,Store Name,https://example.com/product,brand-product-size,Visible product name,Brand,Variant,700 ml,700,ml,0,0,in_stock,none,no,excluded,Mexico; postal code not recorded,knowledge/raw/price-checks/run-YYYY-MM-DD-category-001/example.md,experimental,Replace placeholder values before using this observation.
```

## Evidence Note Template

Create one note per source when a screenshot or raw export is not available.

```md
# Evidence Note

- Run id:
- Observed at:
- Checked by:
- Store:
- Product URL:
- Visible product name:
- Visible price MXN:
- Package size:
- Availability:
- Membership requirement:
- Shipping included:
- Coupon or promotion assumptions:
- Location assumptions:
- Confidence:
- Notes:
```

## Manual Validation Checks

- The timestamp is present and not implied from chat context.
- The product URL points to the observed product or the gap is explicit.
- The package size and unit quantity match.
- The price per unit is recalculated from the visible price.
- Membership, shipping, coupons, and location assumptions are not hidden.
- The observation is marked `unverified` if evidence is incomplete.
