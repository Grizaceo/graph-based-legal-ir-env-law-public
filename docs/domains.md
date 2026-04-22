# Domains

## Domain Strategy

We started with **focused, bounded domains** to validate methodology before attempting broad coverage. Each domain proves the pipeline works end-to-end on a tractable problem.

## Current Domains

### Environmental Law (Pilot)

**Why first:** Bounded regulatory universe, clear procedural paths.

**Coverage:**
- Environmental impact assessment (EIA/SEA)
- Sectoral permits and approvals
- Tribunal Ambiental jurisprudence
- Key regulations (Ley 19.300, Ley 20.417)

**Status:** Ingestion complete, retrieval operational, graph in progress.

### Labor Law (Expansion)

**Why second:** High practical value, large jurisprudence volume, procedural complexity.

**Coverage:**
- Individual labor relations (contracts, dismissal, rights)
- Collective labor law (unions, bargaining, strikes)
- Labor courts (Juzgados del Trabajo, Cortes)
- DT fiscalizaciones and resolutions
- SUSESO social security rulings

**Status:**
- ~4,000 QA pairs consolidated
- PJUD labor scraper operational
- Procurador-digital MVP for procedural deadlines
- Domain-specific BETO fine-tuning

## Planned Domains

### Citizen-Facing (Lexito)

**Purpose:** Simplified retrieval for non-lawyers.

**Scope:**
- Common legal questions (tenancy, consumer, employment basics)
- Plain-language explanations
- Direct citations to sources

**Status:** Concept phase.

### Administrative Law

**Purpose:** Administrative procedure and state liability.

**Scope:** To be defined based on lessons from current domains.

## Domain Validation Checklist

Before a domain is considered "validated":

- [ ] Sources identified and scrapers operational
- [ ] Corpus ingested and indexed
- [ ] QA goldset constructed (min 500 pairs)
- [ ] Retrieval metrics established (MRR, recall)
- [ ] Domain-specific edge cases documented
- [ ] At least one application demonstrates value

## Why Not Full Legal Coverage Now

Attempting all Chilean law at once would:
- Require massive upfront annotation
- Produce lower quality per domain
- Hide domain-specific edge cases
- Overpromise on completeness

Our approach: **prove it works on two domains, then expand with confidence.**