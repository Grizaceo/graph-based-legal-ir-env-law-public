# Repository Policy

## Why Documentation-First

This repository intentionally serves documentation-first. It provides a public technical overview while implementation matures in private repositories.

## Why the Core Remains Private

- **Methodology validation:** proving the approach works on bounded domains first
- **Evaluation integrity:** benchmarks and quality gates require controlled iteration
- **Review workflow maturity:** human validation loops being refined before broader exposure
- **Controlled release:** public surfaces opened gradually to avoid overstating readiness

## Public Release Approach

The strategy is staged:

1. **Documentation** (current) — architecture, methodology, status
2. **Constrained demo** — limited domain, transparent limits
3. **Tools and components** — scrapers, utilities
4. **Broader surfaces** — as quality justifies

## What May Become Public

- Domain goldsets (annotated QA pairs)
- Scrapers and data acquisition tools
- Evaluation datasets (without source PII)
- Methodology documentation

## What Remains Private

- Core graph implementation
- Full vault contents
- Production retrieval infrastructure
- Agent orchestration details

## Incremental Confidence

We started with environmental law. Then labor law. Each domain proves the methodology works before expanding further. This is not a "build everything then release" approach — it's "validate incrementally, release responsibly."