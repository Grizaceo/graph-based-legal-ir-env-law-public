# Graph-Based Legal IR

**Evidence-first legal information retrieval for Chilean law.**

## Project Summary

This project builds an explainable legal information retrieval system for Chilean law, based on an explicit legal graph, exact textual evidence, and human review of ambiguous legal relations.

We started with **focused domain pilots** — environmental law and labor law — to prove the methodology works on constrained scopes before expanding. This incremental approach lets us validate evidence extraction, review workflows, and retrieval quality on tractable problems first.

The objective is not to generate persuasive legal prose. The objective is to build a **verifiable legal retrieval and reasoning substrate** where each relevant relation can be traced to source text and reviewed under controlled criteria.

## Why This Project Exists

Traditional legal search returns documents, keywords, or ranked snippets — but not a verifiable legal structure. Legal LLM workflows produce fluent outputs with limited traceability to exact legal evidence.

For legal work, this is a structural problem:
- Users need to know which source supports which relation
- Users need to distinguish incidental citation from operative legal grounding
- Users need explicit uncertainty and abstention behavior when evidence is insufficient

This repository documents an engineering direction designed to address those constraints directly.

## What Makes This Different

- **Evidence-first design:** relations are grounded in exact textual evidence, not model paraphrase
- **Fail-closed answer path:** when evidence is insufficient, the system abstains or routes to review
- **Human review of ambiguous edges:** legally sensitive ambiguities require explicit human validation
- **Mention vs grounding distinction:** references that mention a norm vs. references that legally ground reasoning
- **Explicit legal graph and review workflow:** graph relations, validation states, and review surfaces are first-class system elements
- **Temporal and procedural compliance:** legal time and process constraints are part of architecture

## Incremental Domain Strategy

We deliberately started with **small, bounded domains** rather than attempting full legal coverage:

1. **Environmental law pilot** — first domain, proved ingestion-to-retrieval pipeline
2. **Labor law expansion** — second domain, validated methodology transfer
3. **Citizen-facing assistant** — simplified retrieval for public use (Lexito)
4. **Future domains** — expand as methodology matures

This approach lets us:
- Validate each component end-to-end before scaling
- Catch domain-specific edge cases early
- Build realistic evaluation benchmarks per domain
- Avoid overpromising on coverage

## Current Scope

- The core development repositories remain private during consolidation
- This public repository contains documentation, architecture, and project context
- Several components are already operational (retrieval, agents, scrapers)
- Public demos planned for constrained surfaces

## System Architecture

High-level layered view:

| Layer | Component | Description |
|-------|-----------|-------------|
| 0 | Scrapers | PJUD, DT, SUSESO, Academia Judicial |
| 1 | IndexO | Retrieval, ranking, BETO fine-tuned encoder |
| 2 | Legal Reviewer | Human curation and validation |
| 3 | Review Graph | Intermediate relations, pending review |
| 4 | Graph-Legal-IR | Canonical graph with hash-verified evidence |
| 5 | LexO-Alpha | Legal reasoning agent |
| 6 | Applications | Procurador-digital, Lexito, case-writer |

See [architecture](docs/architecture.md) and [ecosystem](docs/ecosystem.md) for details.

## Methodological Guarantees

- **Exact evidence spans** for supported relations
- **Traceability** from output claims back to identifiable legal sources
- **Human validation** for ambiguous or high-impact relations
- **Abstention when evidence insufficient** (fail-closed)
- **Separation between reviewed and unreviewed material**

## Intended Audiences

- Legal researchers
- Lawyers and legal analysts
- Legaltech builders
- NLP / IR / knowledge graph researchers

## Documentation

- [Architecture](docs/architecture.md) — system design and layers
- [Ecosystem](docs/ecosystem.md) — full component overview
- [Domains](docs/domains.md) — current domain coverage
- [Methodology](docs/methodology.md) — evidence-first approach
- [Current Status](docs/current-status.md) — what's operational
- [Roadmap](docs/roadmap.md) — development trajectory
- [Public Demo Plan](docs/public-demo-plan.md) — planned public surfaces
- [Repository Policy](docs/repository-policy.md) — release strategy

## Contact

- GitHub: https://github.com/Grizaceo
- LinkedIn: https://www.linkedin.com/in/cristobal-munoz-derecho/
- Email: cristobal.munoz@derecho.uchile.cl