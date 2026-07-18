# Canopy Metadata Generation — Progress Through Phase 4

This README documents the pipeline built and run end-to-end for one study,
covering **Phases 1–4** for the Canopy platform (CoFest 2026).

**Study used:**  — *Nested Pilot Study Comparing Two Treatments
to Reduce Type 2 Diabetes Risk in At-Risk Delawareans* (University of Delaware).

---

## Overview

The goal is a **reusable** workflow that turns heterogeneous study documents
into structured, machine-readable metadata that can be registered as a study in
Canopy. The template (the fields) stays fixed across studies; only the values
change per study.

```
Source Documents  →  Metadata Extraction  →  Structured Metadata (YAML)  →  Canopy Study
 (CTG record,          (map content to           (populated CEDAR              (registered)
  API JSON)             template fields)          template instance)
```

---

## What's done (Phases 1–4)

### Phase 1 — Ingest the source study
- Pulled the ClinicalTrials.gov record and the structured **API v2 JSON**.
- Cross-checked three views for consistency: the public record, the researcher
  view, and the raw JSON.

### Phase 2 — Design the metadata template
- Built a reusable **CEDAR template** (exported as YAML) with all target fields:
  identity, PI, design, population, keywords, data-use, and data-sharing sections.
- Template is study-agnostic — the fields are the same for any study.

### Phase 3 — Populate the template
- Mapped source content into every field: title, PI (Freda Patterson),
  conditions (Prediabetes), design (Randomized · Parallel · Open-Label),
  dates, enrollment (40).
- Generated an **expanded keyword set** beyond the 5 source keywords.
- Filled non-source fields with reasoned values, each flagged for verification.

### Phase 4 — Register in Canopy
- Imported the CEDAR-generated YAML into **Canopy** and generated the study.
- End-to-end path proven for one study: **documents → metadata → registered study**.

---

## Gaps filled manually

These fields are not present in the ClinicalTrials.gov record and were filled
with reasoned values or flagged for verification. They should be confirmed with
the PI or grant documents before submission:

- **NIH Institute / Center** — not in the CTG record
- **FOA Number** — not in the CTG record
- **NIH Program Officer** — not available
- **Access Level** — repository-side decision
- **Estimated Data Size** — not published
- **Data-Use Limitations** — inferred from consent language

---

## Status

| Phase | Description | Status |
|---|---|---|
| 1 | Ingest source study | Complete |
| 2 | Design metadata template | Complete |
| 3 | Populate template | Complete |
| 4 | Register in Canopy | Complete |
| 5 | Apply workflow to a second study (generalization) | Upcoming |
| 6 | Build a metadata quality-evaluation tool | Upcoming |

---

*Prepared for CollaborationFest 2026 (CoFest 2026) — Canopy: AI-Assisted Metadata Generation.*