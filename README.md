# Graph-Based Legal IR for Environmental Law

**Evidence-first legal information retrieval and legal graph modeling for Chilean environmental law.**

## Project Summary

This project aims to build an explainable legal information retrieval system for Chilean environmental law, based on an explicit legal graph, exact textual evidence, and human review of ambiguous legal relations.

The objective is not to generate persuasive legal prose. The objective is to build a verifiable legal retrieval and reasoning substrate where each relevant relation can be traced to source text and reviewed under controlled criteria.

## Why This Project Exists

Traditional legal search usually returns documents, keywords, or ranked snippets, but not a verifiable legal structure. In parallel, many legal LLM workflows produce fluent outputs with limited traceability to exact legal evidence.

For legal work, this is a structural problem:
- users need to know which source supports which relation,
- users need to distinguish incidental citation from operative legal grounding,
- users need explicit uncertainty and abstention behavior when evidence is insufficient.

This repository documents an engineering direction designed to address those constraints directly.

## What Makes This Different

- **Evidence-first design:** relations are expected to be grounded in exact textual evidence, not only model paraphrase.
- **Fail-closed answer path:** when evidence is insufficient or ambiguous, the system should abstain or route to review.
- **Human review of ambiguous edges:** legally sensitive ambiguities are handled with explicit human validation workflows.
- **Mention vs grounding distinction:** the methodology separates references that only mention a norm from references that legally ground reasoning.
- **Explicit legal graph and review workflow:** graph relations, validation states, and review surfaces are treated as first-class system elements.
- **Temporal and procedural compliance as design constraints:** legal time and process constraints are part of architecture and evaluation, not a post-processing patch.

## Current Scope

- The core development repository remains private while the MVP is being consolidated.
- This public repository contains documentation, architecture overview, and publication-facing project context.
- The system is currently in MVP hardening and later conceptual evolution toward LGWM.
- A public demo is planned for a later stage.

## System Architecture

High-level layered view:

1. **Ingestion**
Collect and version legal sources under controlled source policies.

2. **Parsing and canonicalization**
Normalize text and legal units into reproducible canonical artifacts.

3. **Relation extraction**
Produce relation candidates with explicit evidence references.

4. **Graph loading**
Load validated entities and relations into an explicit legal graph model.

5. **Retrieval and planner**
Retrieve relevant graph/text evidence and route through controlled planning logic.

6. **Review**
Apply human review workflows for ambiguity handling and relation validation.

7. **Answer bundle**
Return controlled outputs containing evidence references, scope disclaimers, and abstention when required.

8. **Future transition and state-oriented evolution**
Extend toward timeline/state/transition logic (LGWM-oriented direction) without treating that layer as already production-ready.

## Methodological Guarantees

- **Exact evidence spans** for relevant supported relations.
- **Traceability** from output claims back to identifiable legal sources.
- **Human validation** for ambiguous or high-impact relation classes.
- **Abstention when evidence is insufficient** (fail-closed behavior).
- **Separation between reviewed and non-reviewed material** in retrieval and answer surfaces.

## Intended Audiences

- Legal researchers
- Lawyers and legal analysts
- Legaltech builders
- NLP / IR / knowledge graph researchers

## Current Public Status

> This repository contains public-facing documentation.
> The core development repository remains private while the MVP architecture,
> evaluation pipelines and review workflows are being consolidated.

## Roadmap Snapshot

- **MVP hardening**
- **Review and goldset consolidation**
- **Public demo**
- **Timeline / point-in-time state**
- **Legal transition primitives**
- **LGWM-oriented expansion**

See [architecture](docs/architecture.md), [methodology](docs/methodology.md), [current status](docs/current-status.md), [roadmap](docs/roadmap.md), and [public demo plan](docs/public-demo-plan.md) for details.

## Public Demo

**Public demo: coming later.**

The demo will be released only after core evidence, review, and answer-path controls are stable enough for a responsible public surface.

## Contact

- GitHub: https://github.com/Grizaceo
- LinkedIn: https://www.linkedin.com/in/cristobal-munoz-derecho/
- Email: cristobal.munoz@derecho.uchile.cl
