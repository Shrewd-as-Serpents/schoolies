# Audit Schema Guide: How `infrastructure_critique` Works, and How to Change It

This document explains the design of [`data/sage-audit-schema.json`](../data/sage-audit-schema.json) and the three worked records in [`data/sage-audit-data.json`](../data/sage-audit-data.json). Read this before editing either file. Sections marked **⚠ structural** describe decisions that carry argumentative weight — changing them changes what the project can claim, not just how it looks.

---

## 1. Why `infrastructure_critique` is a sibling, not a nested field ⚠ structural

The original schema (in `website-site-architecture.md`) had one field, `socio_technical_dependency`, buried inside `deconstructive_analysis` as a single free-text string — e.g. `"ZyIndex / Proprietary indexing software & electronic text corpora"`. That's fine as a footnote to a sociology argument. It cannot carry the claim you described: that decolonial sociology and information science are **two co-equal, explicitly named disciplines**.

A reader — especially the IT/data-architecture reader you're targeting — reads structure as an argument. Four top-level sections (`deconstructive_analysis`, `infrastructure_critique`, `reconstructive_ecology`, `reflexive_log`) that each have their own required fields and their own citation pool *says*, before a single sentence is read, "this analysis runs on two independent theoretical engines that both have to fire for a record to be complete." A string nested three levels down inside one discipline's section can't say that. This is the single decision in the schema most worth defending if someone pushes back on "is this really multidisciplinary or just decolonial theory with IT examples sprinkled in."

**If you change this:** don't fold `infrastructure_critique` back into `deconstructive_analysis`, even for brevity. If it feels redundant, the fix is to tighten the *field names*, not to un-flatten the structure.

---

## 2. The `mechanism_type` taxonomy ⚠ structural

```
full_text_indexing | commercial_database_paywall | fixed_schema_data_collection |
qualitative_data_platform | controlled_vocabulary_classification
```

This is a **closed enum**, deliberately, the same way Santos's five monocultures are a closed set — a fixed vocabulary is what makes the coding scheme auditable (Kirk & Miller's reliability standard your protocol already invokes) instead of an open-ended pile of adjectives. Each value names a *class* of system, not a product, which is what lets the taxonomy scale: `ZyIndex` and some future tool are both `full_text_indexing`; `LEXIS/NEXIS` and a future paywalled corpus are both `commercial_database_paywall`.

Only three of the five values are used in the current data (the three records extracted from `decolonial-methods-audit-protocol.md`). `qualitative_data_platform` (for NVivo, mentioned throughout your source docs but never given a full audit entry with a page citation) and `controlled_vocabulary_classification` (for library/metadata classification, which your Section 3 references — Olson, Berman — are about, but which no *textbook passage* has been audited against yet) are there because your citation base already implies them. They're placeholders for records you haven't written yet, not decoration.

**If you add a new mechanism type:** ask whether it's really a new *class* or just a new instance of an existing one. Adding types casually turns this back into an unranked list of adjectives and loses the auditability property. If you're not sure, that's a good moment to re-open this file with me rather than editing the enum solo.

**If you add a new record whose mechanism doesn't fit any of the five:** that's a real signal — it likely means the textbook is doing something your current taxonomy hasn't named yet, which could itself become a paragraph in the write-up ("the audit surfaced a sixth infrastructure category that neither Santos's monocultures nor the initial IS taxonomy anticipated: ___").

---

## 3. Why `is_it_literature` has `minItems: 1` ⚠ structural

Every `infrastructure_critique` must cite at least one `[REF-XXX-YYYY]` id from **Section 3 of `master-reference-key.md`** ("Archival Power, Metadata, & Epistemicide in Information Studies" — Trouillot, Patin et al., Olson, Duarte & Belarde-Lewis, Sutherland, Berman).

This is what makes "information science is a co-equal named discipline here" a checkable claim instead of a framing gesture. Anyone — a reader, an advisor, a peer reviewer from a data-architecture background — can open this JSON and verify: does *every single audit entry* actually engage a real, citable piece of information-science scholarship, or does the IS/IT framing evaporate under a `Ctrl+F` for `[REF-`? Right now, three records, three entries with real citations, zero gaps. Keep it that way as the dataset grows; a record with an empty `is_it_literature` array is a record that's quietly reverted to single-discipline sociology.

---

## 4. Field-by-field reference (the non-structural plumbing)

| Field | Purpose | How free you are to change it |
|---|---|---|
| `record_id` | Stable id, `SAGE-<AUTHOR3>-<YEAR>-P<PAGE>` | Cosmetic format; change the pattern if you outgrow single-textbook audits (e.g. add a source-work code before the page). |
| `source_text.literal_excerpt` | Verbatim quote only | **Never paraphrase here.** This is your Wolcott (2009) transparency layer — the audit trail from quote → tags has to be unbroken, or the "auditability" claim in your own protocol document is undermined by your own data. |
| `deconstructive_analysis.monoculture_tags` | Santos's 5 monocultures, as an array (not a single string) | Made this an array deliberately — two of your three existing records already use two tags each; a single-string field would have forced you to pick one and silently drop the other. |
| `historical_epistemicide_lens.silence_moment` | Trouillot's 4 moments | Kept as an enum for the same auditability reason as `mechanism_type`. |
| `infrastructure_critique.technical_function` | Plain, technically accurate description of what the system does | This is the sentence an IT reader fact-checks first. Write it the way you'd explain the system to another data architect, *before* you say why it's a problem — the gatekeeping critique should follow from an accurate technical description, not substitute for one. |
| `infrastructure_critique.gatekeeping_effect` | The consequence, stated as an effect of the mechanism | Keep this causally downstream of `technical_function` — "because the system does X, therefore Y becomes unfindable" — rather than restating the sociology tags in different words. |
| `reflexive_log.timestamp` | Date of the coding decision | **Currently a known gap, not a design choice** — see §5. |

---

## 5. Something to flag, not fix silently

All three `reflexive_log.timestamp` values are set to `2026-08-30`, because that's the only date your source documents actually give (a single reflexive note in `sage-methods-critique-v2 (1).md`). I did not invent per-record dates. Your own protocol builds in **diachronic reliability** — re-coding after a 14-day interval to check that a tag boundary holds — which only works if you're tracking *real* per-entry coding dates. Worth deciding: are these three records genuinely all coded on one day, or should each carry its actual date once you have it? Right now the data can't tell the difference between "audited once, same day" and "we didn't record when."

There's also an unresolved discrepancy I didn't try to silently resolve: `decolonial-methods-audit-protocol.md` and `sage-methods-critique-v2 (1).md` each quote a *different* sentence from Altheide p. 153 (the "one big file" passage vs. the "documents of documents... will continue to emerge" passage). I used the protocol document's excerpt as canonical since it's the more fully worked-out audit entry, but if the "documents of documents" line is the one you actually want to lead with (it has the "emerge, be reborn" language your CDA layer analyzes), that's a one-line swap in `source_text.literal_excerpt` — flag it back to me and I'll make the change and update `rhetorical_device` to match.

---

## 6. How to add a new record

1. Pick a passage from the SAGE text (or another audited work) with a page citation.
2. Fill `source_text` first, verbatim.
3. Tag `deconstructive_analysis` using the Tier 1–3 vocabulary already defined in `decolonial-methods-audit-protocol.md` §2.1 — don't invent new monoculture/historical-lens codes; that vocabulary is Santos's and Grosfoguel's, not yours to extend.
4. Fill `infrastructure_critique`: pick (or, per §2, deliberately extend) a `mechanism_type`, describe the real technical function, state the gatekeeping effect, and cite at least one Section 3 reference.
5. Fill `reconstructive_ecology` as the Santos-ecology answer to whichever monoculture(s) you tagged in step 3.
6. Validate the file still parses — `ConvertFrom-Json` in PowerShell, or any JSON linter — before committing.

---

`✶ Insight ─────────────────────────────────────`
- **Schema-as-argument**: making `infrastructure_critique` a sibling section rather than a nested field is the same move information architects make when they promote a field to its own table in a database — it's a statement about what's a first-class entity versus what's an attribute of something else. Here it's doing double duty: it's good data modeling *and* it's the structural proof of your thesis.
- **The `fixed_schema_data_collection` record is your strongest IS/IT bridge**: "precoded protocol variables decided before data collection" is *literally* schema-on-write versus schema-on-read, a live debate in data architecture (rigid relational schemas vs. flexible/NoSQL models). That parallel didn't need any theoretical stretching — it's the same design tension, just applied to human narrative instead of database rows.
- **Closed enums as a reliability instrument, not just tidiness**: Kirk & Miller's reliability standards (which your own protocol already invokes) and a closed JSON `enum` are solving the same problem from two disciplines — both exist to make sure two different coders (or two different runs of the same coder) converge on the same tag. That's a nice one-sentence bridge if you ever want to explicitly name the methodological parallel in the write-up, not just the object-level one.
`─────────────────────────────────────────────────`
