# AGENTS.md

Token-light operating instructions for AI agents working in this repository.

## Mission

This repo is the durable operating memory for `radar-de-ofertas`: a project for researching, validating, and eventually reusing workflows that detect and compare offers in Mexico.

Start with evidence and small reusable memory. Do not jump from a single idea or price comparison into a skill, plugin, or automation.

## Read Order

Read only what is needed for the task.

1. `AGENTS.md` - stable agent rules and routing.
2. `PROJECT_AI_PROFILE.md` - project facts, scope, constraints, and definition of done.
3. `docs/specs/adopcion-reuse-promotion-guide/PRD.md` - adoption rationale and acceptance criteria.
4. `knowledge/README.md` - memory contract and evidence lifecycle.
5. `knowledge/projects/radar-de-ofertas/README.md` - project memory index.
6. `knowledge/projects/radar-de-ofertas/reuse-backlog.md` - reusable candidates before promotion.
7. `knowledge/projects/radar-de-ofertas/source-index.md` - source registry when evidence matters.

Do not bulk-read `knowledge/raw/` or `knowledge/processed/` unless exact evidence is needed.

## Operating Rules

- Treat chat as coordination and files as durable memory.
- Preserve evidence for price, product, availability, process, and recommendation claims.
- Separate verified facts, inferred claims, experimental ideas, and open questions.
- Use the smallest durable asset that preserves value and traceability.
- Update memory only when the learning is reusable.
- Record reusable candidates in `knowledge/projects/radar-de-ofertas/reuse-backlog.md`.
- Promote deliberately: `idea/process -> evidence -> insight -> experiment -> doc/template -> skill -> plugin -> automation`.
- Do not create `skills/`, `plugins/`, or automations without validated manual runs and explicit user approval.
- Always report validation performed, or state why validation was not possible.

## Memory Routing

- Project profile: `PROJECT_AI_PROFILE.md`
- Durable project memory: `knowledge/projects/radar-de-ofertas/`
- Reuse candidates: `knowledge/projects/radar-de-ofertas/reuse-backlog.md`
- Source index: `knowledge/projects/radar-de-ofertas/source-index.md`
- Raw evidence: `knowledge/raw/`
- Processed summaries and insights: `knowledge/processed/`
- Specs, decisions, and runbooks: `docs/`
- Future installable workflows: `skills/`
- Future packaged capabilities: `plugins/`

## Reuse Promotion

- Save as `knowledge/` when it is evidence, an insight, an experiment, or an open question.
- Promote to `docs/` or templates when it becomes a reusable process for people or agents.
- Promote to `skills/` only when Codex should repeatedly execute the same expert workflow.
- Promote to `plugins/` only when the workflow needs packaged scripts, tools, APIs, assets, or integrations.
- Promote to automation only after a manual run, review, failure-case handling, and approval.

Before promoting, verify:

- The candidate has evidence or explicitly marked assumptions.
- Inputs, outputs, and done condition are clear.
- Manual validation exists for docs/templates, skills, plugins, or automations.
- The asset does not duplicate an existing doc, skill, plugin, or workflow.
- The token budget impact is reasonable.

## Escalation

Ask the user before making broad product, architecture, security, credential, billing, deployment, scraping, or automation decisions.
