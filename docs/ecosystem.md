# The LexCon Ecosystem

The LexCon ecosystem is a layered legal infrastructure, not a single model or a single app. Its job is to keep acquisition, review, canonicalization, reasoning, and public presentation separated enough that each layer can be inspected on its own.

---

## Component map

### Layer 0-1: acquisition and retrieval
- `n8n-judicial` — public-source acquisition and normalization
- `IndexO` — semantic retrieval and ranking over the legal corpus
- `sentence-index` — deterministic surfacing and lighter-weight navigation

### Layer 2-3: human review and relation state
- `legal-reviewer` — labeling, curation, and goldset production
- `review-graph` — pending / approved / rejected / expired lifecycle for relations

### Layer 4-5: grounded legal reasoning
- `graph-legal-ir` — canonical graph with promoted relations and evidence gates
- `LexO` — reasoning harness that operates only over grounded, reviewable material
- Subagents — specialized workers used inside the reasoning harness when a task benefits from decomposition

### Layer 6: public and product surfaces
- `LexCon-hub` — public entry point and navigation layer
- `lexito` — citizen-facing assistant surface
- `lexo-citizen-assistant` — simplified orientation layer
- `lexo-case-writer` — drafting support with evidence constraints
- `procurador-digital` — procedural support for deadlines and workflow

---

## Public vs private boundary

The public repository documents the system; it does not expose the vault, the raw review queues, or internal work-in-progress. That boundary is intentional.

The public story should remain readable without revealing:
- private corpora
- raw PII-bearing artifacts
- unstable prototypes
- internal scratch notes
- lab-only shortcuts that would mislead external readers

---

## Current strategic focus

1. evidence-first legal IR
2. bounded domain pilots
3. reviewability before canonicalization
4. public surfaces that can be explained clearly
5. release hygiene that avoids hype and internal clutter

---

## Domain strategy

The ecosystem currently emphasizes:
- environmental law
- labor law
- procedural support as a downstream application layer

Those domains are not chosen because they are easy. They are chosen because they are legible enough to prove the method.

---

## Scalability posture

The ecosystem is designed to grow without losing traceability.

That means:
- new domains must inherit the same evidence rules
- review states must remain explicit
- canonical promotion must remain human-governed
- public claims must remain bounded by actual coverage
