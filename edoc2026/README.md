# EDOC 2026 Artefacts

## Formal Definitions of Core Concepts in Enterprise Ontology

**Paper:** *Formal Definitions of Core Concepts in Enterprise Ontology*
**Authors:** Edwin de Haan, Marien R. Krouwel, and Henderik A. Proper
**Conference:** EDOC 2026

---

## Overview

This directory contains all artefacts produced for the EDOC 2026 paper. The paper formalises three core superconcepts of Enterprise Ontology's (EO) Factual Information (FI) theory using Formal Concept Analysis (FCA). Each concept is analysed in its own subdirectory; the analysis of each concept produces 31 formally defined (sub)concepts in total.

The three concepts analysed are, in order of dependency:

| Concept | Description |
|---------|-------------|
| **Object** | A persisting, bare identity — the primitive carrier of identity in FI theory, on which Feature and Thing depend |
| **Feature** | A predicate assignable to an Object — either unary (assigned to a single Object) or binary (assigned to a pair of Objects) |
| **Thing** | An Object with an assigned Form (the collection of its Features) |

The analysis follows the dependency order: Object is formalised first, its formal definitions are used as input for the Feature analysis, and both are used as input for the Thing analysis.

---

## Formalisation Procedure

The artefacts in each concept directory correspond to the five steps of the formalisation procedure (Sections 3.2–3.3 of the paper):

**Step A — Extract concept discourse**
The discourse pertaining to the concept and its subconcepts is extracted from the source text sentence by sentence. Characteristics of the EO concepts, related EO terms, constraints, and canonical examples are identified. Each sentence is referenced using the notation `<page-number>-<sentence-number>` to support traceability to the source text (Dietz & Mulder, 2024).

**Step B — Extend formal context with characteristics**
The FCA formal context is extended with the characteristics of the EO concept. Interpretive challenges encountered in the extracted discourse are identified and resolved within EO's own paradigm (see Section 3.2 of the paper for the eight categories of interpretive challenges and their resolution strategy).

**Step C — Extend formal context with items and characteristics relations**
Each canonical example from the extracted discourse is added as an item to the formal context. The characteristics that hold for each example are recorded, and examples are validated for consistency with the stated characteristics of their concept.

**Step D — Derive formal concepts**
Formal concepts are derived from the completed formal context using FCA. Each derived concept consists of an extension (the set of items that share a set of characteristics) and an intension (the set of characteristics that hold for all items in the extension). The derived concepts are validated against constraints extracted in earlier steps, and the isomorphism between term characteristics and derived concepts is verified. An AI-assisted traceability validation is performed at this step.

**Step E — Construct term definitions and constraints**
For each non-trivial formal concept, a term definition is constructed from its intension, referring to its superconcept (genus) and specifying only the differentiating characteristics. Disjointness and completeness constraints are recorded. All definitions are validated against the ISO 1087 standard and checked for common ontological modelling pitfalls using the OOPS! criteria. An AI-assisted validation of the definitions is performed at this step.

---

## Directory Structure

```
edoc2026/
├── README.md               ← this file
├── prompts/                ← AI validation prompts & definition checklist
├── owl/                    ← OWL/XML document for reasoning
├── Object/
│   ├── step_a/
│   ├── step_b/
│   ├── step_c/
│   ├── step_d/
│   └── step_e/
├── Feature/
│   ├── step_a/
│   ├── step_b/
│   ├── step_c/
│   ├── step_d/
│   └── step_e/
└── Thing/
│   ├── step_a/
│   ├── step_b/
│   ├── step_c/
│   ├── step_d/
│   └── step_e/
```

Each concept directory contain steps subdirectories, corresponding to the steps of the formalisation procedure. The artefacts produced in each step differs; see procedure.

---

## File Descriptions

The different file types possibly encountered in steps are described below. Files are named consistently across concepts and steps; replace `<Concept>` with `Object`, `Feature`, or `Thing`.

| File | Description |
|------|-------------|
| `<Concept>_<Step>_Cycles.pdf` | **Cyclic procedure steps PDF** — describes each cycle performed within the given step; for each analysis it provides the input sentence, followed by the extracted knowledge. When an interpretive challenge is encountered, the issue is flagged, resolution options are provided and the chosen option is documented. After an interpretive challenge, a cycle starts anew from the first sentence. |
| `<Concept>_<Step>_Discourse.pdf` | **Discourse PDF** — contains the input text, together with the interpretation of each sentence. Each sentence is annotated with its `<page-number>-<sentence-number>` reference to the source text (Dietz & Mulder, 2024). Identified interpretive challenges and their resolutions are recorded inline. Note that the output of each concept's analysis serves as input for the next: Object starts from the original source text; Feature incorporates the output of Object; Thing incorporates the output of Feature. |
| `<Concept>_<Step>_Formalcontext.pdf` | **Formal context PDF** — contains the complete formal context table (items × characteristics). Each item and characteristic is referenced by `<page-number>-<sentence-number>` when traceable to the source text, or marked `-` when no source reference exists (e.g. for placeholder entries). Each relationship in the table is marked `X` when the item–characteristic relationship is explicitly stated in the source text, or `#` when it is derived by applying FI theory. Disjointness and completeness constraints between sibling concepts are also recorded here. |
| `<Concept>_<Step>_formalcontext.cxt` | **FCA context file** — the formal context in the standard `.cxt` format, suitable for use with FCA tools such as [fcaR](https://github.com/Malaga-FCA-group/fcaR) and the [ODIS online FCA tool](https://odis-web.github.io/). This file is produced from the formal context at the end of step D and can be used to independently reproduce the derived concepts. |
| `<Concept>_<Step>_derived_concepts.txt` | **Derived concepts** — lists all formal concepts derived from the formal context. Each concept entry specifies its extension (the set of canonical examples that are instances of the concept) and its intension (the set of characteristics that hold for every item in the extension). These derived concepts form the basis for the term definitions constructed in step E. |
| `<Concept>_<Step>_Validation_Report.pdf` | **Validation report** — contains the AI-assisted validation, generated using Claude AI Sonnet 4.6 (Anthropic, 2026) with the prompt from the `prompts/` directory. For a formal context, the report validates the traceability of each item, each characteristic, and each relationship in the formal context against the recorded source references. For a set of definitions, the report validates them against a checklist that ensures ISO 1087 adherence. Any issues flagged by the AI assistant and the subsequent human review are noted in the report. |
| `<Concept>_<Step>_Definitions.pdf` | **Definitions PDF** — contains the term definitions constructed from the formal context. Each definition refers to the intension of its superconcept, includes the differentiating characteristics of the formal concept, and excludes cyclic characteristics to prevent definitional loops. Disjointness and completeness constraints between sibling concepts are also recorded here. |

---

## Notation

The notation used throughout these artefacts follows the conventions established in the the paper:

- Sentence references: `<page-number>-<sentence-number>` (e.g. `56-17` refers to sentence 17 on page 56 of Dietz & Mulder, 2024)
- Bracket conventions in formal context tables:
  - **[ ]** = Concrete
  - **( )** = Conceptual
  - **⟨ ⟩** = Abstract
- Placeholder items and placeholder terms are marked explicitly in each table and carry no source reference (`-`)
- Formal context relationships: **X** = explicitly stated in source text; **#** = derived by applying FI theory; **-** = no relationship

---

## AI Validation Disclosure

As disclosed in the paper's Acknowledgements, Claude AI Sonnet 4.6 (Anthropic, 2026) was used as an automated validation tool at steps D and E of the formalisation procedure. The prompts used are available in `edoc2026/prompts/` (see the main README for details). All substantive interpretive decisions were made by the human authors. Any AI-suggested corrections incorporated into the artefacts are explicitly noted in the corresponding validation reports.

---

## Source Text

All sentence references in these artefacts point to:

> Dietz, J.L.G. and Mulder, H.B.F., *Enterprise Ontology — A Human-Centric Approach to Understanding the Essence of Organisation*, Second Edition, Springer (2024).
