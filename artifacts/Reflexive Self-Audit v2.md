# Reflexive Self-Audit: Turning the Protocol on Its Own Instrument

*Companion to [`docs/ethical-professional-standards.md`](ethical-professional-standards.md) §5 and [`docs/audit-schema-guide.md`](audit-schema-guide.md). This document applies the project's own coding tiers ([`data/codebook.json`](../data/codebook.json)) to the project's own artifacts — the audit data schema and the coding practice it implements — rather than to Altheide's text. It is written to the same standard the rest of this project holds itself to: no tier is applied where it does not precisely fit, and no parallel is drawn without a citation anchoring it.*

## Why This Is Required

Part II of this project's methodology turns Altheide's own Ethnographic Content Analysis back onto his text, on the argument that a method's neutrality claim should never go unexamined by its own users. The same argument, applied one level further, requires the same treatment of this project's coding protocol. This is not an infinite regress: it stops at one level, for reasons stated at the end of this document, not because recursion is exhausting but because a further pass would not surface anything not already disclosed here.

## Where the Self-Audit Applies

**Tier 1 — Monoculture of Knowledge and Rigor (`MONO_KNOWLEDGE`).** The audit data schema requires every unit of analysis to resolve into a fixed set of English-language, machine-readable JSON fields before it counts as a valid coded record. This is structurally the same operation `MONO_KNOWLEDGE` names when applied to Altheide's own reliance on ZyIndex-searchable text (see `SAGE-ALT-1996-CH5-11` in `sage-audit-data-final.json`): a format requirement quietly functioning as an admissibility requirement.

**Tier 1 — Monoculture of the Dominant Scale (`MONO_SCALE`).** Reducing a full paragraph to two or three short enum codes (e.g. `MONO_KNOWLEDGE`, `MONO_PRODUCTIVITY`) necessarily discards the passage's full situated particularity in favor of a small, closed, reusable vocabulary. This is dominant-scale abstraction by definition, and it is also the precondition for the auditability Kirk and Miller (1986) require (`[REF-KIR-1986]`): the tension is real and is not resolved by disclosing it, only made visible.

**Tier 1 — Monoculture of Linear Time (`MONO_TIME`), partial.** Already logged in [`docs/site-architecture.md`](site-architecture.md) §5: the Coding Trail's strict sequential reveal risks re-enacting linear-time monoculture. Not repeated in full here; see that document for the reasoning and the argument for why it is an acceptable, disclosed trade-off rather than a disqualifying flaw.

**Tier 2 — Extraction / Vacuum-Packing (`EXT_VACUUM_PACK`).** See [`docs/ethical-professional-standards.md`](ethical-professional-standards.md) §5 for the full statement. In short: the mechanism polanco et al. (2020) name is structurally present in how this project's own data is built; the object and stakes the term was coined to describe are not present in the same way, and the paragraph is careful not to claim otherwise.

**Tier 5 — Infrastructure Critique (`fixed_schema_data_collection`).** This is the least metaphorical claim in this document: the audit data schema *is* a schema-on-write data model, in exactly the sense `docs/audit-schema-guide.md` already uses to explain the concept to an IT reader. Fields and enums were fixed before any of the eight current verification-queue records were coded. A passage that did not fit an existing `monoculture_tags` enum value or `evidence_type` value would have no destination in the record — the same gatekeeping effect this project attributes to Altheide's precoded protocol structure and Figure 3.2 pipeline (`SAGE-ALT-1996-CH3-FIG3-2`).

**Tier 5, a narrower point.** The `record_id` field's validation pattern (`^SAGE-[A-Z]{3}-[0-9]{4}-(CH[0-9]+(-FIG[0-9]-[0-9])?|P[0-9]+)$`) presumes the audited object is a paginated, chaptered work with an identifiable author and year. It cannot represent a born-digital artifact — this document, or the schema file itself — without a workaround, because the instrument was built to audit texts like Altheide's, not artifacts like its own. This is stated as a precise limit of the schema's current design, not extended into a larger claim.

## Where the Self-Audit Does Not Apply, Stated Explicitly

**Tier 3 — Historical Bias-Lenses.** Grosfoguel's (2013) four genocides/epistemicides name specific, documented historical violences against specific human populations (`[REF-GRO-2013]`). None of the four historical lenses is mapped onto this project's own coding schema here, and none should be. Doing so would not be a decolonial insight; it would be a category error — treating a JSON file's design choices as commensurate with the conquest of Al-Andalus, Indigenous genocide, the Atlantic slave trade, or the European witch trials. Declining to force this tier is the same methodological discipline this project already commits to in Part V of its methodology, where reconstructions requiring standing the researcher does not have are marked *unresolved* rather than filled in.

## Where the Reconstruction Already Exists

The reconstructive answer to the Tier 1 and Tier 5 self-critiques above is not new: it is the Coding Trail's stepped-reveal interaction model, already built and documented in `docs/site-architecture.md` §5. Presenting the literal excerpt alone, unannotated, before any coded tag is allowed to appear, and disclosing the reflexive log only after the analytic work is done, functions as an `ECO_KNOWLEDGES`-style restoration of situated, thick context ahead of coded abstraction — applied to this project's own method, not only argued for it. The reconstruction preceded the self-audit that names it; this document is making explicit what the interaction-model decision was already doing.

## Why the Recursion Stops Here

A further audit of this self-audit — applying the tiers to this document's own prose — would restate the same terms already disclosed above (fixed vocabulary, discarded particularity, a schema-on-write structure) without surfacing a new erasure. Continuing past this point would be recursion in service of demonstrating recursion, not in service of the original Honors question. This document treats that as a stopping condition, consistent with Part V's commitment to bounded, honest reconstruction over open-ended speculation.
