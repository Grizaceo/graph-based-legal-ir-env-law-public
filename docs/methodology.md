# Methodology

## Evidence-First

The project prioritizes verifiable legal evidence over fluent summarization. Relevant relations should be grounded in explicit source text.

## Fail-Closed

When evidence quality or coverage is insufficient, the system should abstain or escalate to review instead of fabricating certainty.

## Exact Snippets

Evidence references are expected to point to exact snippets or spans, enabling precise legal inspection and reproducibility.

## Human Validation

Ambiguous legal relations are reviewed by humans before being used as trusted output components.

## Mention vs Grounding

A key methodological distinction is between:
- **Mention:** a source cites or references another source contextually.
- **Grounding/Foundation:** the cited source is materially used to support legal reasoning.

Conflating these roles produces legal retrieval errors and misleading outputs.

## Temporal and Procedural Compliance

Legal validity depends on timing and procedure. Methodology and architecture must handle temporal state and procedural constraints explicitly, not implicitly.

## Why Explainability Matters in Legal AI

In legal contexts, correctness is not enough if reasoning cannot be inspected. Explainability enables:
- traceability,
- accountable review,
- clear uncertainty handling,
- safer integration into legal research workflows.
