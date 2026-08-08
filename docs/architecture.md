# Architecture & Core Guarantees

The system is built around a simple legal constraint: retrieval is only useful if the evidence path can be inspected.

The architecture therefore separates acquisition, retrieval, human review, canonicalization, and reasoning into distinct layers. That separation is what keeps the system explainable and fail-closed.

---

## The layered stack

| Layer | Name | Primary responsibility |
|---|---|---|
| 0 | Scrapers / acquisition | Gather public materials from PJUD, DT, SUSESO, BCN/LeyChile, and other approved sources |
| 1 | IndexO + sentence-index | Semantic and deterministic retrieval for candidate evidence |
| 2 | legal-reviewer | Human curation, labeling, and goldset construction |
| 3 | review-graph | Relation lifecycle: pending, approved, rejected, expired |
| 4 | graph-legal-ir | Canonical graph with hash-backed evidence and promotion gates |
| 5 | LexO | Reasoning harness, subagent coordination, and grounded response path |
| 6 | LexCon-hub + public apps | Public navigation, orientation, and constrained user-facing surfaces |

---

## Core design principles

### 1. Exact evidence first
Every promoted relation must point to a textual anchor that can be inspected directly. Paraphrase is not enough.

### 2. Human validation for ambiguous edges
If a relation is legally sensitive, uncertain, or contested, it belongs in review before it becomes canonical.

### 3. Fail-closed answer path
If the system cannot support a claim with sufficient evidence, it should abstain or route to review instead of improvising certainty.

### 4. Traceability by construction
The canonical graph is not a bag of notes. It is a traceable structure where each edge can be checked against source text and review state.

### 5. Mention is not grounding
A source can mention another source without legally relying on it. The architecture keeps those roles distinct.

### 6. Temporal and procedural awareness
Legal validity depends on time, sequence, and procedural conditions. The architecture treats those as first-class constraints.

---

## Canonical relation lifecycle

A relation typically moves through these states:

PENDING → APPROVED
PENDING → REJECTED
PENDING → EXPIRED

Only approved material can be promoted into the canonical graph. Expired material does not silently linger as truth.

---

## Data flow summary

Public sources → acquisition → retrieval index → candidate evidence → review-graph → canonical graph → LexO reasoning → public or product surfaces

At the review stage, the relation can move to one of three outcomes:
- approved → canonical graph
- rejected → archive / non-canonical
- expired → requeue or retire

---

## What this architecture is optimized for

- explainable legal IR
- exact evidence inspection
- bounded retrieval on specific legal domains
- reviewable promotion of relations
- abstention rather than speculation

## What it is not optimized for

- generic chat
- broad legal advice without evidence
- unreviewed relationship mining
- replacing legal professionals
