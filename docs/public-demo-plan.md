# Public Demo Plan

## Objective

Show that the system can retrieve legal material in a way that is explainable, bounded, and honest about uncertainty.

The demo should prove the method, not oversell the scope.

## Demo story

A user asks a bounded legal question.
The system returns:
- candidate evidence
- exact textual snippets
- relation traceability
- review state where relevant
- an answer or an abstention, depending on evidence quality

## What the demo must show

1. domain-limited query handling
2. exact evidence inspection
3. relation traceability
4. fail-closed abstention when support is weak
5. a visible distinction between reviewed and unreviewed material
6. clear scope disclaimers

## First demo domain

Labor law is the leading candidate because it is:
- practically relevant
- naturally bounded
- easy to explain to a public audience
- compatible with the system's current evidence-first method

Environmental law remains the other core pilot and can be shown as a second example when needed.

## What the demo must not show

- full legal coverage claims
- autonomous legal advice
- unreviewed relations presented as canonical
- private vault contents
- internal lab clutter
- anything that makes the demo look broader than it really is

## Release gate ✓
- [x] the architecture story is clean
- [x] the public docs are coherent
- [x] the evidence narrative is consistent
- [x] the system can visibly abstain when evidence is insufficient

## Implementation

The demo is implemented as a single-page interactive prototype (`demo.html`) that simulates the LexCon retrieval pipeline:

- **Client-side knowledge base** with 5 curated labor law queries covering Código del Trabajo, Ley 20.123, and associated jurisprudence
- **Evidence-first flow:** each query returns candidate evidence with exact textual snippets, review state tags (reviewed/unreviewed), and traceability panels
- **Abstention behavior:** queries outside the domain (or with insufficient reviewed evidence) return a clear abstention with explanation
- **Scope disclaimer:** persistent banner clarifying this is a method demo, not legal advice
- **Visual distinction between reviewed and unreviewed material:** color-coded tags, dot indicators in trace panels, summary counts
- **Full LexCon visual identity:** dark theme, bento grid, pipeline metaphor, accent glow

## One-line public description

An evidence-first legal retrieval demo that shows how grounded legal systems should answer only when the record is strong enough.
