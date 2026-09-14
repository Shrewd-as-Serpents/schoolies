# Decoding Absences

A decolonial audit of a qualitative-research-methods textbook, read through two named disciplines: **decolonial sociology** (Santos, Grosfoguel, Castro-Gómez, polanco et al.) and **information science / critical data studies** (Trouillot, Patin et al., Olson, Duarte & Belarde-Lewis) — arguing that indexing systems, metadata schemas, and database access are not neutral technical infrastructure but active gatekeepers of what counts as legible, findable knowledge.

The audited object is David L. Altheide's *Qualitative Media Analysis*, originally published by SAGE in 1996 and examined through the 2011 SAGE Research Methods digital presentation (DOI: [10.4135/9781412985536](https://doi.org/10.4135/9781412985536)).

## Who this is for

Two audiences, deliberately: a sociology/decolonial-studies reader, and an **IT/data-architecture reader** — the people who design the classification systems, CMS platforms, and metadata taxonomies this project argues are never epistemically neutral.

## Structure

```
data/       Structured, machine-readable project data (the "code" of this project)
  sage-audit-schema.json   JSON Schema for an audit record (2 named disciplines coded per record)
  sage-audit-data.json     The actual audited textbook passages, fully coded
  codebook.json            Full definitions for every short code used in sage-audit-data.json
  references.json          Structured bibliography (machine-readable version of docs/master-reference-key.md)

docs/       Prose: theory, method, bibliography, and how the data model works
  theoretical-framework.md   The argument: epistemicide, zero-point hubris, and why infrastructure is the second discipline
  methodology.md             The six-step audit protocol, and where each step lives in data/
  audit-schema-guide.md      Field-by-field guide to the schema -- what's safe to edit, what's structurally load-bearing
  master-reference-key.md    Full annotated bibliography (human-reading copy)
  site-architecture.md       IA/UX spec for the not-yet-built interactive website

assets/     Non-text project assets (mind map, etc.)

archive/original-drafts/   Superseded prose drafts, kept for reference -- their content has been
                            consolidated into data/ and docs/ above. Nothing here is authoritative;
                            check docs/ and data/ first.
```

## Start here

1. [`docs/theoretical-framework.md`](docs/theoretical-framework.md) — the argument, in prose.
2. [`docs/methodology.md`](docs/methodology.md) — how the argument becomes a coding protocol.
3. [`data/sage-audit-data.json`](data/sage-audit-data.json) — the protocol applied to real textbook passages.
4. [`docs/audit-schema-guide.md`](docs/audit-schema-guide.md) — if you're going to add a new audited passage or change the data model.

## Status

Data model and three worked audit records: done. Interactive website (per `docs/site-architecture.md`): not started.
