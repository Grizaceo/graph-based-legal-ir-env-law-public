# Architecture

## Why a Legal Graph

Legal analysis requires more than document retrieval. Practitioners need explicit legal structure: which sources relate to which claims, under what role, and with what evidence. A legal graph models entities and relations as inspectable objects rather than implicit text patterns.

## System Layers

### Layer 0: Scrapers

Collect legal sources from Chilean institutions:
- PJUD (sentencias, resoluciones)
- DT (fiscalizaciones)
- SUSESO (security social rulings)
- Academia Judicial (training materials)
- LeyChile / BCN (normative)

### Layer 1: IndexO / Retrieval

Semantic retrieval infrastructure:
- BETO encoder fine-tuned on Chilean legal QA
- 768-dimensional embeddings
- Vault with ~3,000 legal documents
- Domain-specific ranking models

### Layer 2: Legal Reviewer

Human curation layer:
- Deep review window (full document labeling)
- Quick triage window (relation validation)
- Goldset construction for evaluation
- Quality gates for downstream layers

### Layer 3: Review Graph

Intermediate relations layer:
- Machine-suggested relations pending review
- State machine: PENDING → APPROVED / REJECTED / EXPIRED
- Prevents unvalidated relations from entering canonical graph
- Cola estructurada para revisión humana

### Layer 4: Graph-Legal-IR (Canonical)

Canonical legal graph:
- Only reviewed, approved relations enter
- Hash-verified evidence for each relation
- Temporal metadata (validity periods)
- Designed for transparency and auditability

### Layer 5: LexO-Alpha

Legal reasoning agent:
- Operates over graph + vault + live retrieval
- Generates Normative Interaction Frames (structured legal reasoning)
- 9 specialized subagents for different tasks
- Telegram gateway for direct interaction

### Layer 6: Applications

End-user products:
- Procurador-digital: procedural deadline calculator
- Lexito: citizen-facing assistant
- lexo-case-writer: document drafting
- lexo-simulated-trial: training environment

## Role of Canonicalization

Canonicalization is a core control point. It provides reproducible text units and stable references used downstream by extraction, graph loading, review, and retrieval. Without canonicalization, evidence traceability degrades quickly.

## Human Review Integration

Human review is integrated into the architecture, not treated as optional. Ambiguous legal edges are reviewed before they enter high-confidence answer paths. The review graph state machine ensures nothing is forgotten or assumed valid.

## Retrieval and Reasoning

The retrieval layer (IndexO + BETO) provides candidates. The reasoning layer (LexO-Alpha) assembles evidence, applies legal logic, and knows when to abstain. The graph layer provides verified structure.

## Fail-Closed Answer Path

Answer generation is constrained by evidence availability and review status. If support is insufficient or unreviewed, the system abstains rather than fabricating confidence.

## Data Flow

```
Sources → Scrapers → Vault → IndexO
                              ↓
         Relations → Review Graph → Canonical Graph
                              ↓
                      LexO-Alpha → Applications
```