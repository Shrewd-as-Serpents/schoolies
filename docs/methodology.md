# Methodology: Qualitative Multimodal Document Audit

*Consolidated from `decolonial-methods-audit-protocol.md` §§2-5 and `sage-methods-critique-v2 (1).md` Parts II, III & V. Originals preserved in [`archive/original-drafts/`](../archive/original-drafts/). Theory this methodology operationalizes: [`docs/theoretical-framework.md`](theoretical-framework.md).*

## Why Audit a Textbook

This project treats a qualitative-research-methods textbook as a **primary document** — an empirical, analyzable social product — rather than a neutral instructional manual.

> **Primary-source control statement.** The primary work audited in this project is David L. Altheide's *Qualitative Media Analysis*, originally published by SAGE in 1996. The work was accessed through its SAGE Research Methods digital presentation, whose platform record displays a 2011 publication date and is identified by DOI `10.4135/9781412985536`. This project uses **Altheide (1996)** for formal academic citation, historical interpretation, and audit-record identifiers. It uses the SAGE Research Methods chapter title and downloadable PDF page as the stable locator for the digital text consulted. The 2011 platform date is recorded as access-platform metadata, not treated as a new or revised edition.

Auditing the textbook itself, rather than making an abstract theoretical argument, turns the literature review into a meta-critique of how an academic discipline enforces what Santos calls the "monoculture of knowledge and rigor" — using Altheide's *own* method, **Ethnographic Content Analysis (ECA)** — the reflexive, recursive, constant-comparative analysis of documents — turned back onto his guide.

## The Six-Step Operational Coding Protocol

```
  1. SEGMENT THE TEXT           (written text, visual diagrams, sample protocols)
                    v
  2. LITERAL PASS                (Wolcott's base layer: record content descriptively)
                    v
  3. MONOCULTURE CODING          (Santos's five lenses: tag active epistemic erasures)
                    v
  4. RHETORICO-DISCURSIVE &      (CDA lexical choices; infrastructure mechanism --
     INFRASTRUCTURE ANALYSIS      indexing, database, schema, classification)
                    v
  5. HISTORICAL BIAS-LENS        (Trouillot's silences mapped to Grosfoguel's genocides)
     MAPPING
                    v
  6. REFLEXIVE AUDIT             (interpretive reliability / positionality log)
```

1. **Analytical Segmentation** — the manual is broken into written text (sentence/paragraph units), visual diagrams (treated as unified multimodal units, e.g. Altheide's Fig. 3.2 "Logic of Protocol Analysis"), and sample protocols (e.g. his 11-segment TV news coding protocol).
2. **The Literal Pass** — the coder records the literal string or visual layout only, zero interpretation. This is the auditable base layer (Wolcott's transparency criterion). In the data model, this is `source_text.literal_excerpt` — see [`data/sage-audit-schema.json`](../data/sage-audit-schema.json).
3. **Monoculture Coding** — each unit is tagged against Santos's five monocultures. Full code definitions: [`data/codebook.json`](../data/codebook.json) → `tier_1_monocultures`. In the data model: `deconstructive_analysis.monoculture_tags`.
4. **Rhetorico-Discursive & Infrastructure Analysis** — a *discursive* layer (Fairclough-style CDA: which lexical choices manufacture authority — "rigor," "systematic," "standardized") run alongside an *infrastructure* layer that names the specific technical mechanism the passage depends on (an indexing engine, a paywalled database, a fixed data-collection schema — see [`docs/theoretical-framework.md`](theoretical-framework.md) §4). In the data model: `deconstructive_analysis.rhetorical_device` and the sibling `infrastructure_critique` section.
5. **Historical Bias-Lens Cross-Referencing** — each monoculture tag is mapped to one of Grosfoguel's four historical epistemicides and one of Trouillot's four moments of archival silence. Codes: `data/codebook.json` → `tier_3_historical_lenses`. In the data model: `deconstructive_analysis.historical_epistemicide_lens`.
6. **Reflexive Audit** — the coder logs their own positionality and interpretive decisions, satisfying Kirk & Miller's (1986) reliability standard. In the data model: `reflexive_log`.

The reconstruction phase (Santos's Ecologies answering each tagged Monoculture) is Tier 4 — `data/codebook.json` → `tier_4_ecologies`, and `reconstructive_ecology` in the data model.

## Qualitative Reliability Standard (Kirk & Miller, 1986)

Every coded record must be defensible against three distinct reliability tests, applied during coding and logged in `reflexive_log`:

- **Quixotic Reliability** — guarding against a code being applied mechanically to every surface-level mention (e.g. not tagging *every* reference to software as extractive).
- **Diachronic Reliability** — re-coding the same passage after a time interval (the protocol used 14 days) and confirming the tag boundary holds.
- **Synchronic Reliability** — cross-checking a text tag against a second mode (a visual diagram) or a second, independent coder, and confirming consensus.

## Where the Audited Entries Live

The three fully worked audit entries (ZyIndex/full-text indexing, p.153; precoded protocol variables, p.158; LEXIS/NEXIS commercial access, p.174) are **data, not prose** — see [`data/sage-audit-data.json`](../data/sage-audit-data.json). Each record carries its literal excerpt, its Tier 1-3 sociology coding, its Tier 5 infrastructure-critique coding (the IS/IT discipline), its Tier 4 reconstructive ecology, and its reflexive log, all validated against [`data/sage-audit-schema.json`](../data/sage-audit-schema.json). Longer-form prose walkthroughs of each entry, as originally drafted, remain available in [`archive/original-drafts/`](../archive/original-drafts/) if a fuller narrative treatment is wanted for the final write-up.

## Looking Ahead: Reconstruction as the Second Methodology

This is the first of two linked methodologies. Once the SAGE guide's systematic erasures are mapped, the second methodology — **Decolonial Reconstruction** — returns to the tagged units and "holds them open" to their corresponding ecologies, modeling what a cognitive-justice option looks like on the academic page, rather than only criticizing from a distance.

## Integration with the Research Website

This methodology, its codebook, and its data feed the interactive site described in [`docs/site-architecture.md`](site-architecture.md): the split-screen textbook viewer (Module A) and the Absence ↔ Ecology matrix toggle (Module B) both render directly from `data/sage-audit-data.json`.
