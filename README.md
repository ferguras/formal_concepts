# Formal Definitions of Core Concepts in Enterprise Ontology
## Artefact Repository

**Paper:** *Formal Definitions of Core Concepts in Enterprise Ontology: A Foundation for Machine-Verifiable Implementation Traceability*
**Authors:** Edwin de Haan, Marien R. Krouwel, and Henderik A. Proper
**Submitted to:** EDOC 2026

---

## Overview

This repository contains all artefacts produced during the formalisation of the three core superconcepts of Enterprise Ontology's (EO) Factual Information (FI) theory: **Object**, **Feature**, and **Thing**. The artefacts support the claims made in the paper and enable independent verification of the formal concept definitions, their traceability to the EO discourse, and their conformance to quality criteria.

The formalisation approach is grounded in Formal Concept Analysis (FCA) and operates exclusively within EO's own theoretical paradigm. Every item, characteristic, and interpretive challenge resolution recorded here is referenced by page and sentence number to the source text: Dietz, J.L.G. and Mulder, H.B.F., *Enterprise Ontology — A Human-Centric Approach to Understanding the Essence of Organisation*, Second Edition, Springer (2024).

---

## Notation

Throughout the formal context tables, sentence references follow the notation used in the paper:
> **(p** ***page-number***, **s** ***sentence-number*** **)** refers to a specific sentence on a specific page of Dietz & Mulder (2024).
The artefact uses page-number-sentence-number keys.

Bracket conventions in the formal contexts are:
- **[ ]** = Concrete
- **( )** = Conceptual
- **⟨ ⟩** = Abstract

Placeholder items and placeholder terms — added where the discourse lacks a canonical example or leaves a formal concept unnamed — are marked explicitly in each table: they do not have a reference to the discourse.

---

## Reproducing the OWL Reasoning Results

The reasoning results reported in Section 5.2 of the paper can be reproduced using the HermiT OWL 2 Reasoner (Glimm et al., 2014) against `edoc2026/owl/fi_core_concepts.owl`. 
HermiT is available as a plug-in for Protégé (https://protege.stanford.edu) and can be invoked directly from the Reasoner menu after loading the OWL file.

---

## AI Validation Disclosure

As disclosed in the paper's Acknowledgements, Claude AI Sonnet 4.6 (Anthropic, 2026) was used as an automated validation tool to cross-check traceability links between the formal contexts and the EO discourse. All substantive interpretive decisions were made by the human authors. The prompts submitted are available in `edoc2026/prompts` and the full validation reports are available in the concept directory. A report lists if any intervention was needed to correct reasoning. 

---

## Contact

Correspondence regarding the artefacts should be directed to the first author.
All substantive questions about the formalisation approach and interpretive decisions are addressed in the paper.
