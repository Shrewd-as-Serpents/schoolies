# Information Architecture \& UX Wireframe Specification

## Project: *Decoding Absences: A Decolonial Framework for Textual Reconstruction*

This specification defines the information architecture, interactive site map, UI component wireframes, and frontend JSON data schema for building the honors research website.

> **Implementation note:** the `audit-records.json` schema sketched in §3 below has since been implemented as [`data/sage-audit-schema.json`](../data/sage-audit-schema.json), with real records in [`data/sage-audit-data.json`](../data/sage-audit-data.json), a `data/codebook.json` for the full coding vocabulary, and a `data/references.json` for the bibliography. It also gained a fifth, IS/IT-facing coding tier (`infrastructure_critique`) not yet reflected in the wireframes below; see [`docs/theoretical-framework.md`](theoretical-framework.md) §4 and [`docs/audit-schema-guide.md`](audit-schema-guide.md) for why. The site itself (the actual pages this spec describes) has not been built yet.

\---

## 1\. Interactive Site Map \& Navigation Hierarchy

```
\[ Research Site Root ]
 ├── 1.0 Home / Landing Page
 │    ├── Hero Banner: "The Zero-Point Hubris of Qualitative Methodologies"
 │    ├── Interactive Abstract (Santos, Grosfoguel, Castro-Gómez, SAGE Audit)
 │    └── Quick-Start Guided Tour (Deconstruction → Reconstruction Pipeline)
 │
 ├── 2.0 Theory Matrix (Epistemic Foundations)
 │    ├── 2.1 The Sociology of Absences (Santos's 5 Monocultures)
 │    ├── 2.2 Historical Epistemicides (Grosfoguel \& Trouillot Lenses)
 │    ├── 2.3 The Zero-Point Hubris \& "iCloud Researcher" (Castro-Gómez \& polanco et al.)
 │    └── 2.4 Mechanics of Language Control (Bennett's EAD Monoculture)
 │
 ├── 3.0 SAGE Methods Audit Engine (First Methodology)
 │    ├── 3.1 Qualitative Multimodal Document Analysis Protocol
 │    ├── 3.2 Interactive SAGE Textbook Viewer (Altheide 2011)
 │    └── 3.3 The 6-Step Decolonial Coding Pipeline
 │
 ├── 4.0 Interactive Coding Matrix \& Database
 │    ├── 4.1 Live Search \& Filter (Filter by Monoculture, Epistemicide, Software Tool)
 │    ├── 4.2 Interactive Toggle: "Deconstructive Absence" ↔ "Reconstructive Ecology"
 │    └── 4.3 Raw Audit Data Exporter (JSON / CSV Download)
 │
 ├── 5.0 Decolonial Reconstruction Lab (Second Methodology)
 │    ├── 5.1 Santos's 5 Ecologies in Practice
 │    ├── 5.2 Standpoint \& Member-Checking Validation Protocols
 │    └── 5.3 Pedagogical Counter-Manuals \& Alternative Syllabi
 │
 └── 6.0 Reflexive Audit \& Epistemic Location
      ├── 6.1 Positionality Log (Kirk \& Miller Reliability Checks)
      └── 6.2 Full Bibliography \& Source Repository
```

\---

## 2\. Page-by-Page UI/UX Wireframe Specifications

### Module A: SAGE Textbook Interactive Document Viewer (Section 3.2)

* **Layout**: Split-screen interface.

   * **Left Pane (Primary Text)**: Rendered digitized excerpts from David L. Altheide's *Qualitative Media Analysis* (1996), examined through the 2011 SAGE Research Methods digital presentation, with interactive text-highlighting. Chapter title and SRM PDF page identify the stable digital source location.
  * **Right Pane (Audit Card)**: Dynamic card displaying active codes for the currently selected line or visual flowchart:

    * *Literal Pass*: Exact string transcription.
    * *Monoculture Tag*: Badge indicating which of Santos's 5 Monocultures is operating (e.g. `\[Monoculture of Knowledge \& Rigor]`).
    * *Socio-Technical Erasure*: Highlighted software/database assumptions (e.g., `LEXIS/NEXIS`, `NVivo`, `ZyIndex`).
    * *Historical Epistemicide Lens*: Pop-over modal linking to historical source documentation (e.g., Grosfoguel's conquest of Al-Andalus or Atlantic slavery).
    * *Reflexive Auditor Note*: Personal positionality log entry.

### Module B: The Monoculture-to-Ecology Matrix Toggle (Section 4.2)

* **UI Behavior**: An interactive dual-state toggle button (`\[Show Absence / Deconstruction]` vs. `\[Show Presence / Reconstruction]`).
* **Deconstructive State**: Displays red/amber analytical callouts pointing out what the SAGE text renders "ignorant, residual, inferior, local, or unproductive."
* **Reconstructive State**: Smoothly animates into a green/teal callout displaying Santos's corresponding Ecology (Knowledges, Temporalities, Recognition, Trans-scale, Productivities), complete with qualitative validity rationale (e.g., Wolcott's thick description).

\---

## 3\. Frontend JSON Data Schema for Audit Records

Developers or static site generators (Astro, SvelteKit, React, or Eleventy) can import the following JSON schema (`audit-records.json`) to populate the interactive database:

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "title": "DecolonialAuditRecord",
  "type": "object",
  "properties": {
    "record\_id": { "type": "string", "example": "SAGE-ALT-1996-CH5-11" },
    "source\_text": {
      "author": "David L. Altheide",
      "work": "Qualitative Media Analysis",
      "year": 1996,
      "digital\_platform": "SAGE Research Methods",
      "digital\_platform\_record\_year": 2011,
      "doi": "https://doi.org/10.4135/9781412985536",
      "stable\_locator": { "chapter\_title": "Electronic Reality", "srm\_pdf\_page": "11 of 12" },
      "literal\_excerpt": "Recent software development in word processors and database managers has helped solve this problem... The system I have found useful is called Zyindex... which basically treats everything stored in files as 'one big file!'"
    },
    "deconstructive\_analysis": {
      "monoculture\_tag": "Monoculture of Knowledge and Rigor",
      "erased\_entity": "Non-digitized, oral, vernacular, and non-English archival formats",
      "rhetorical\_device": "Techno-positivistic efficiency rhetoric",
      "socio\_technical\_dependency": "ZyIndex / Proprietary indexing software \& electronic text corpora",
      "historical\_epistemicide\_lens": {
        "framework": "Grosfoguel (2013) \& Trouillot (1995)",
        "erasure\_type": "Colonization of memory via standardized archival indexing",
        "citation": "Grosfoguel, 2013, p. 77; Trouillot, 1995, p. 26"
      }
    },
    "reconstructive\_ecology": {
      "ecology\_tag": "Ecology of Knowledges",
      "restored\_presence": "Oral history archives, embodied storytelling, and community-held memory repositories",
      "qualitative\_method\_value": "Thick Description \& Radical Co-presence",
      "validation\_criterion": "Kirk \& Miller (1986) Synchronic Reliability \& Member-Checking"
    },
    "reflexive\_log": {
      "coder\_positionality": "Audited from a student standpoint recognizing institutional access privilege to SAGE databases.",
      "timestamp": "2026-08-30T21:40:00Z"
    }
  }
}
```

\---

## 4\. CSS Color Palette \& Epistemic Design System

* **Base Surface**: `#0F172A` (Deep Slate / Abyssal Space)
* **Monoculture / Absence Accent**: `#EF4444` (Crimson / Epistemic Erasure)
* **Reconstruction / Ecology Accent**: `#10B981` (Emerald / Restored Presence)
* **Zero-Point Critique Accent**: `#6366F1` (Indigo / "iCloud Researcher" Unmasking)
* **Typography**:

  * Body: Inter / Sans-Serif (High Legibility for Academic Reading)
  * Headings: Newsreader / Serif (Editorial Authority)
  * Data/Code: JetBrains Mono (Audit Code Precision)

