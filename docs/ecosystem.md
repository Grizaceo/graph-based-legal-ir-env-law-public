# Ecosystem

## Overview

The project has evolved from a single-domain IR system into a **layered legal technology ecosystem**. Each layer is independently useful but gains power when connected.

## Layer Architecture

```
Layer 0: Scrapers          → Raw data acquisition
Layer 1: IndexO            → Retrieval and ranking
Layer 2: Legal Reviewer    → Human validation
Layer 3: Review Graph      → Pending relations
Layer 4: Graph-Legal-IR    → Canonical legal graph
Layer 5: LexO-Alpha        → Legal reasoning agent
Layer 6: Applications      → End-user products
```

## Layer Details

### Layer 0: Scrapers

Data acquisition from Chilean legal sources:

| Source | Type | Status |
|--------|------|--------|
| PJUD (sentencias) | Judicial decisions | Operational |
| DT (fiscalizaciones) | Labor inspections | Operational |
| SUSESO | Social security rulings | Operational |
| Academia Judicial | Judicial training | Operational |
| LeyChile | Normative (via BCN) | Operational |

### Layer 1: IndexO

Retrieval infrastructure:
- **BETO fine-tuned encoder** trained on Chilean legal QA
- Semantic search over ~3,000 documents in vault
- Domain-specific ranking for labor and environmental law
- Goldset evaluation with MRR@10 metrics

### Layer 2: Legal Reviewer

Human curation layer:
- Two review windows (deep review, quick triage)
- Label taxonomy for document classification
- Goldset construction for evaluation
- Quality control for downstream graph

### Layer 3: Review Graph

Intermediate relations layer:
- Machine-suggested relations pending review
- State machine: PENDING → APPROVED → REJECTED → EXPIRED
- Prevents zombie edges from accumulating
- Bridge between extraction and canonical graph

### Layer 4: Graph-Legal-IR

Canonical legal graph:
- Hash-verified evidence for each relation
- Only reviewed, approved relations enter
- Temporal metadata (when relation applies)
- Designed for legal reasoning transparency

### Layer 5: LexO-Alpha

Legal reasoning agent:
- Operates over graph + vault
- Generates Normative Interaction Frames
- 9 specialized subagents (researcher, judge, writer, etc.)
- Telegram gateway for direct interaction

### Layer 6: Applications

End-user products:

| Product | Purpose | Status |
|---------|---------|--------|
| Procurador-digital | Procedural deadline calculator | MVP (labor), in dev (executive) |
| Lexito | Citizen-facing legal assistant | Concept |
| lexo-case-writer | Legal document drafting | Concept |
| lexo-simulated-trial | Training environment | Concept |

## Key Repositories

| Repo | Layer | Visibility |
|------|-------|------------|
| n8n-judicial | 0 | Private |
| indexo-retriever-prod | 1 | Private |
| legal-ecosystem | 2-3 | Private |
| graph-legal-ir (core) | 4 | Private |
| lexo-research-lab | 5 | Private |
| procurar-digital | 6 | Private |
| graph-based-legal-ir-env-law-public | Docs | Public |

## Design Principles

1. **No raw model output → canonical graph.** Everything reviewed.
2. **Fail-closed by default.** Insufficient evidence = abstain.
3. **Temporal awareness.** Legal relations exist in time.
4. **Separation of concerns.** Each layer does one thing well.
5. **Auditability.** Every claim traceable to source.