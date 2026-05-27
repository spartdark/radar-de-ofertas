# Knowledge Memory Contract

This directory stores durable project memory for `radar-de-ofertas`.

Use it to preserve evidence, insights, experiments, decisions, open questions, and reusable candidates. Keep files concise and indexed so Codex can load the smallest useful context.

## Directory Model

```txt
knowledge/
  README.md
  raw/
    price-checks/
    promo-checks/
  processed/
    insights/
    summaries/
  projects/
    radar-de-ofertas/
      README.md
      work-log.md
      reuse-backlog.md
      source-index.md
      offer-watchlist.md
```

## Evidence Lifecycle

Use this flow:

```txt
idea/process -> evidence -> insight -> experiment -> doc/template -> skill -> plugin -> automation
```

Rules:

- Raw evidence belongs in `knowledge/raw/`.
- Promotion and bank-route evidence also belongs in `knowledge/raw/`, usually under `promo-checks/` unless it is tied to a specific product price.
- Normalized summaries and atomic insights belong in `knowledge/processed/`.
- Project-specific memory belongs in `knowledge/projects/radar-de-ofertas/`.
- Reusable process docs belong in `docs/` only after validation.
- Skills, plugins, and automations require explicit promotion decisions.

## Confidence Labels

- `verified`: backed by direct evidence that can be checked.
- `inferred`: reasoned from available evidence but not directly proven.
- `experimental`: plausible and being tested.
- `unverified`: captured but not yet checked.

## Price Evidence Minimum

For price comparisons, prefer entries that include:

- product;
- store;
- URL;
- checked date and time;
- visible price;
- package size;
- availability;
- membership, shipping, coupon, and location assumptions;
- confidence label.

If any field is missing, mark it explicitly instead of hiding the gap.

## Current Memory Map

- `knowledge/projects/radar-de-ofertas/README.md`: shortest project index and active decisions.
- `knowledge/projects/radar-de-ofertas/work-log.md`: chronological summary of validated work sessions and outputs.
- `knowledge/projects/radar-de-ofertas/source-index.md`: source registry for raw evidence and timestamps.
- `knowledge/projects/radar-de-ofertas/reuse-backlog.md`: candidates before promotion to docs, skills, plugins, or automation.
- `knowledge/projects/radar-de-ofertas/offer-watchlist.md`: products worth rechecking; not purchase recommendations.

## Promotion Rule

Before promoting any candidate beyond `knowledge`, it must be recorded in `knowledge/projects/radar-de-ofertas/reuse-backlog.md` with:

- status;
- source;
- current artifact;
- proposed asset;
- reuse case;
- expected users;
- inputs;
- outputs;
- evidence needed;
- validation needed;
- token budget impact;
- decision;
- open questions;
- risks.
