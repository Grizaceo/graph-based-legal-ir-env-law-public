# Methodology

## Evidence-first

The project prioritizes verifiable legal evidence over fluent summarization.
Relevant relations should be grounded in explicit source text.

## Fail-closed

When evidence quality or coverage is insufficient, the system should abstain or escalate to review instead of fabricating certainty.

## Exact snippets

Evidence references should point to exact snippets or spans whenever possible.
That makes legal inspection reproducible and lowers the chance of citation drift.

## Human validation

Ambiguous legal relations are reviewed by humans before they are treated as trusted output components.

## Mention vs grounding

A key distinction is between:
- mention: a source references another source contextually
- grounding: the cited source materially supports the legal reasoning

Conflating those roles creates legal retrieval errors.

## Traceability

A system is only explainable if the chain from claim to evidence can be reconstructed.
Traceability is therefore a system property, not a stylistic preference.

## Temporal and procedural compliance

Legal validity depends on time and procedure.
The architecture and the public story should both respect that reality.

## Why explainability matters

In legal AI, correctness is not enough if the reasoning cannot be inspected.
Explainability enables:
- accountable review
- clearer uncertainty handling
- safer public communication
- better integration into legal workflows

## Practical rule

If the evidence is weak, the system should be willing to say so.
