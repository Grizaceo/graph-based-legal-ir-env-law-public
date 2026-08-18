# Legal Graph Explorer

Public documentation and release harness for evidence-first legal information retrieval in Chilean law.

This repository is intentionally public-facing. It documents the architecture, methodology, release posture, and demo surface of the LexCon / LexO ecosystem without exposing vault contents, private execution traces, or lab-only implementation details.

The central promise is simple:
- exact textual evidence before conclusion
- traceable relations before promotion
- fail-closed abstention when evidence is insufficient
- human review for ambiguous or high-impact relations

## What this repo is for

This repo is the public story of a system that does not want to be clever first. It wants to be verifiable first.

It packages:
- the architecture of the layered legal IR stack
- the evidence-first methodology
- the current status of the public release surface
- the release policy and demo plan
- a compact narrative suitable for GitHub and portfolio review

## What this repo is not

- not the private vault
- not the internal notebook of the lab
- not a claim of full legal coverage
- not autonomous legal advice
- not a place for raw corpora, unreviewed outputs, or half-finished internal experiments

## Scope: law as a graph, not case law

This repository publishes **the law itself** — statutes and codes rendered as a
knowledge graph of legal units (UMJs) and their normative relations. It does
**not** publish judicial decisions, sentences, RITs, tribunal metadata, or any
case-level data. The graph data (`graph-data/umj-laboral.json`) contains only
normative nodes (laws and articles) and their `contains` edges.

Case law and jurisprudence are deliberately out of scope for this public
surface. If you are looking for the case-law layer, it lives in the private
ecosystem, not here.

## Current ecosystem view

| Layer | Component | Role |
|---|---|---|
| 0 | n8n-judicial | Acquisition and normalization from public legal sources |
| 1 | IndexO + sentence-index | Retrieval, ranking, and surfacing of candidate evidence |
| 2 | legal-reviewer | Human curation, labels, and goldset construction |
| 3 | review-graph | Pending / approved / rejected / expired relation lifecycle |
| 4 | graph-legal-ir | Canonical graph with hash-backed evidence and human validation gates |
| 5 | LexO | Reasoning harness and subagent orchestration over grounded evidence |
| 6 | LexCon-hub + public apps | Public-facing navigation, orientation, and product surfaces |

## Why this matters

Traditional legal search gives documents, keyword hits, or fluent answers without a stable evidence path. This project is built to solve a narrower but more important problem: how to make legal retrieval explainable, auditable, and safe to trust.

That means the system must be able to say:
- where a relation came from
- why it was promoted
- what evidence supports it
- when it should refuse to answer

## Documentation map

- [Architecture](docs/architecture.md) — layered stack and guarantees
- [Ecosystem](docs/ecosystem.md) — component map across LexCon / LexO
- [Domains](docs/domains.md) — current domain focus and expansion path
- [Methodology](docs/methodology.md) — evidence-first and fail-closed principles
- [Current Status](docs/current-status.md) — honest snapshot of the release surface
- [Roadmap](docs/roadmap.md) — public-release trajectory
- [Public Demo Plan](docs/public-demo-plan.md) — what a bounded demo shows
- [Repository Policy](docs/repository-policy.md) — what stays public vs private
- [Release Notes](docs/release-notes.md) — narrative summary for GitHub

## Short version for GitHub

What it does:
- documents an evidence-first legal IR architecture
- explains the review graph and canonical graph split
- shows how LexO reasons only over grounded material
- provides a public-facing release harness with clear limits

Why it matters:
- legal AI is only useful when its evidence path can be inspected
- public trust requires abstention, not confident guessing
- the same architecture that helps researchers also reduces risk for productization


## Contact

- GitHub: https://github.com/Grizaceo
- LinkedIn: https://www.linkedin.com/in/cristobal-munoz-derecho/
- Email: cristobal.munoz@derecho.uchile.cl
