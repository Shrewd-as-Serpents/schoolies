# Verification Checklist (v2)

*Status of every bibliographic claim in this project. The edition conflict flagged in v1 is now resolved. This version separates what is verified, what is background context from a discarded citation path, and what still requires literal-wording verification against the SRM PDFs before any record can be promoted out of the verification queue.*

---

## 1. Edition conflict — RESOLVED

**Primary-source control statement.** The primary work audited in this project is David L. Altheide's *Qualitative Media Analysis*, originally published by SAGE in 1996. The work was accessed through its SAGE Research Methods digital presentation, whose platform record displays a 2011 publication date and is identified by DOI `10.4135/9781412985536`. This project uses **Altheide (1996)** for formal academic citation, historical interpretation, and audit-record identifiers. It uses the SAGE Research Methods chapter title and downloadable PDF page as the stable locator for the digital text consulted. The 2011 platform date is recorded as access-platform metadata, not treated as a new or revised edition.

**Resolution.** The primary source audited in this project is confirmed as **David L. Altheide (1996), *Qualitative Media Analysis*, SAGE Publications, Inc.**, DOI [10.4135/9781412985536](https://doi.org/10.4135/9781412985536), accessed through the SAGE Research Methods (SRM) digital chapter-download platform. The SRM record resolving from this DOI lists the publication year as 1996 and the sole author as David L. Altheide.

**Why 1996 and not 2011 or 2013.** An earlier pass in this project labeled the digital edition "2011," a date that does not appear on the SAGE Research Methods record itself. Checking the DOI directly shows a Pub. Date of 1996. A separate 2013 second edition, co-authored with Christopher J. Schneider, is a materially different, differently-paginated text (WorldCat OCLC 820790765) and is **not** the object audited in this project.

**What changed as a result:**
- Every record ID prefix changed from `SAGE-ALT-2011-` to `SAGE-ALT-1996-`.
- Every citation now reads Altheide, D. L. (1996) rather than Altheide (2011) or Altheide & Schneider (2013).
- All page locators use SRM chapter + SRM PDF page only (e.g., "Ch. 5, p. 11 of 12"); no print-edition page number is used as a final citation anywhere in this project.

---

## 2. Verified externally — background on the discarded 2013 path

These facts about the 2013 second edition remain true, but that edition is **not** the audited source. They are kept here only so a reader can see why the earlier draft's citations were wrong and why they were changed, not as citations this project relies on.

| Claim | Status | Source of verification |
| --- | --- | --- |
| A 2013 second edition exists, co-authored with Christopher J. Schneider | Verified (background only) | WorldCat OCLC 820790765; SAGE Research Methods |
| Print ISBNs 9781452230054 / 1452230056; eText 9781452289052 | Verified (background only) | VitalSource; AbeBooks; Amazon listing |
| Series: Qualitative Research Methods, vol. 38; publisher SAGE, Thousand Oaks | Verified (background only) | WorldCat OCLC 820790765 |
| Extent of the 2013 second edition: xiii, 150 pages | Verified (background only) | WorldCat OCLC 820790765; Internet Archive |
| Extent of the 1996 first edition: viii, 87 pages (print) | Verified | Internet Archive |
| Both editions share the same eight chapter titles | Verified | WorldCat (2013); Semantic Scholar (1996) |

**Verified table of contents (shared by both editions' chapter titles):**

1. Plugged in Research
2. Ethnographic Content Analysis
3. Process of Qualitative Document Analysis
4. Newspapers, Magazines, and Electronic Documents
5. Electronic Reality I
6. Electronic Reality II
7. Tracking Discourse
8. Field Notes and Other Data

Note: the SRM digital chapter downloads used for this audit's page locators paginate each chapter independently (e.g., "Ch. 5, p. 11 of 12"), which is why SRM page counts do not need to be reconciled against either edition's print extent.

---

## 3. Current verification-queue records — none promoted to findings yet

Every record below has a stable SRM digital locator and an honest `evidence_type` label, but none has had its literal wording re-checked character-for-character against the SRM PDF. This is the correct, honest state for a project at this stage — a record with `quote_checked: false` must not be treated as `verbatim_quote`.

| Record ID | SRM Locator | Evidence Type | Quote Checked | Status |
| --- | --- | --- | --- | --- |
| `SAGE-ALT-1996-CH5-11` (ZyIndex) | Ch. 5, p. 11 of 12 | close_paraphrase | No | Verification queue |
| `SAGE-ALT-1996-CH5-04` (VCR Counters) | Ch. 5, p. 4 of 12 | close_paraphrase | No | Verification queue |
| `SAGE-ALT-1996-CH3-12` (Cross-Case Subsumption) | Ch. 3, p. 12 of 24 | analytical_summary | No | Verification queue |
| `SAGE-ALT-1996-CH5-05` (LEXIS/NEXIS) | Ch. 5, p. 5 of 12 | analytical_summary | No | Verification queue |
| `SAGE-ALT-1996-CH3-FIG3-2` (ECA Diagram) | Ch. 3, p. 5 of 24, Fig. 3.2 | diagram_description | No | Verification queue |
| `SAGE-ALT-1996-CH2-06` (Intercoder Reliability) | Ch. 2, p. 6 of 13 | close_paraphrase | No | Verification queue |
| `SAGE-BEN-2014-P061` (English Academic Discourse) | Part II, p. 61 | close_paraphrase | No | Verification queue |
| `SAGE-POL-2020-P084` (Vacuum-Packing) | Section 3, p. 84 | close_paraphrase | No | Verification queue |

**One contradiction fixed in this pass.** `SAGE-ALT-1996-CH5-11` was previously logged with `evidence_type: verbatim_quote` while its own status noted the quotation was still under verification. That is a contradiction — a record cannot claim verbatim status and unresolved wording at the same time. It has been downgraded to `close_paraphrase` here and must stay there until the literal wording is checked against Ch. 5, p. 11 of 12, at which point it can be promoted to `verbatim_quote`.

---

## 4. Requires the SRM PDF in hand; cannot be checked externally

- [ ] For each of the eight records above, open the corresponding SRM chapter PDF and compare the excerpt word-for-word, including ellipses.
- [ ] Promote a record's `evidence_type` to `verbatim_quote` only after that word-for-word check passes; otherwise leave it at `close_paraphrase`, `analytical_summary`, or `diagram_description`.
- [ ] Confirm the Figure 3.2 caption and flow-step labels against Ch. 3, p. 5 of 24, before promoting `SAGE-ALT-1996-CH3-FIG3-2`.
- [ ] Confirm the Bennett (2014) and polanco et al. (2020) excerpts against their own source PDFs (these do not have an edition-conflict problem, only an unchecked-wording one).

---

## 5. Reliability documentation status

Kirk and Miller (1986) reliability tests (quixotic, diachronic, synchronic) have **not yet been logged** for any of the eight current records under their new IDs. Earlier project drafts logged reliability checks against a different, now-retired ID scheme (`SAGE-ALT-2013-P153/P158/P174`); those logs do not automatically transfer to the renamed 1996-identity records, since the citation object underneath them changed. This project reports that status honestly rather than carrying old checks forward under a new label.

| Record | Diachronic | Synchronic | Quixotic |
| --- | --- | --- | --- |
| `SAGE-ALT-1996-CH5-11` | not_completed | not_completed | not_completed |
| `SAGE-ALT-1996-CH5-04` | not_completed | not_completed | not_completed |
| `SAGE-ALT-1996-CH3-12` | not_completed | not_completed | not_completed |
| `SAGE-ALT-1996-CH5-05` | not_completed | not_completed | not_completed |
| `SAGE-ALT-1996-CH3-FIG3-2` | not_completed | not_completed | not_completed |
| `SAGE-ALT-1996-CH2-06` | not_completed | not_completed | not_completed |
| `SAGE-BEN-2014-P061` | not_completed | not_completed | not_completed |
| `SAGE-POL-2020-P084` | not_completed | not_completed | not_completed |

---

## 6. Verified as accurate in the reference list

- Hartman, S. V. (2008). Venus in two acts. *Small Axe, 12*(2), 1–14. [https://doi.org/10.1215/-12-2-1](https://doi.org/10.1215/-12-2-1). Added after correcting an earlier misattribution of "critical fabulation" to Santos; the term is Hartman's.

## 7. Recommended checks on the remaining bibliography

Not errors, but not independently confirmed in this pass:

- [ ] Castro-Gómez: the reference list gives 2005 in one place and 2010 in another. Confirm which edition of *La hybris del punto cero* is being cited and standardize.
- [ ] Grosfoguel (2013): confirm whether the article is cited from *Human Architecture: Journal of the Sociology of Self-Knowledge*, 11(1), 73–90, or *Revista Tabula Rasa* — it appeared in both venues.
- [ ] Confirm page numbers given for in-text citations of Grosfoguel (p. 77, p. 78) and Trouillot (p. 26, p. 29) in the audit records.
- [ ] Bennett (2014): confirm the exact volume title and page range, which differ slightly between the literature review and the reference list.

---

## 8. Note on what this checklist demonstrates

A project arguing that archives and citation infrastructure determine what counts as findable knowledge is a project whose own citation layer is part of its argument. Finding, and fixing, a wrong publication year on its own primary source — twice, first "2013," then "2011," before landing on the verified "1996" — is not a failure of the method; it is the method being applied reflexively to itself and correcting on the evidence. That correction is recorded here, in `decolonial-methods-audit-protocol-v4.md`, and in every per-record `source_text.year` field in `sage-audit-data-final.json`, rather than corrected silently.
