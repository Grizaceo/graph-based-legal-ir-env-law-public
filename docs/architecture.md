# Architecture

## Why a Legal Graph

Environmental legal analysis requires more than document retrieval. Practitioners need explicit legal structure: which sources relate to which claims, under what role, and with what evidence. A legal graph supports this by modeling entities and relations as inspectable objects rather than implicit text patterns.

## System Layers

1. **Ingestion layer**
Collects legal sources and metadata from curated inputs.

2. **Parsing and canonicalization layer**
Transforms sources into stable canonical text units and normalized identifiers.

3. **Relation extraction layer**
Generates candidate legal relations with evidence references.

4. **Graph loading layer**
Loads entities and validated relations into the legal graph.

5. **Retrieval and planner layer**
Routes queries through evidence-aware retrieval and controlled planning logic.

6. **Review layer**
Supports human triage and validation of ambiguous or high-impact relations.

7. **Answer path layer**
Produces controlled answer bundles with evidence links and abstention behavior.

## Role of Canonicalization

Canonicalization is a core control point. It provides reproducible text units and stable references used downstream by extraction, graph loading, review, and retrieval. Without canonicalization, evidence traceability degrades quickly.

## Relation Extractor

The extractor proposes relation candidates between legal entities and attaches evidence references. These candidates are not all treated as final truth. They pass through validation logic and, where necessary, human review.

## Human Review

Human review is integrated into the architecture, not treated as a downstream optional step. Ambiguous legal edges are reviewed before they enter high-confidence answer paths.

## Retrieval and Planner

The retrieval/planner stage is designed to prioritize supported legal evidence over free-form generation. The planner controls how evidence is assembled and when the system must abstain.

## Controlled Answer Path

Answer generation is constrained by evidence availability and validation status. If support is insufficient, the system should not produce a confident legal claim.

## MVP Core and Future Evolution

The current public architecture describes an MVP-oriented explainable retrieval core. A future evolution targets timeline/state/transition logic (LGWM-oriented direction), but this should be understood as an active conceptual and engineering trajectory, not as a fully public production layer.
