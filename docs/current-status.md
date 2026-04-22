# Current Status

## What Is Operational

### Scrapers (Layer 0)
- PJUD laboral scraper: operational, regular downloads
- DT investigations: operational
- SUSESO: operational via JSONP workaround
- Academia Judicial: operational via Vimeo transcripts
- LeyChile: bulk download capability

### Retrieval (Layer 1)
- IndexO vault: ~3,000 documents indexed
- BETO encoder: fine-tuned on legal QA
- MRR@10: 0.6256 (plateaued, hard negatives pending)
- Domain retrieval: environmental and labor operational

### Review (Layer 2)
- Windows A/B defined
- Label taxonomy established
- Goldset growing (manual addition)

### Review Graph (Layer 3)
- State machine designed
- Awaiting full implementation

### Agents (Layer 5)
- LexO-Alpha: operational via Telegram
- 9 subagents defined
- Normative Interaction Frame methodology established

### Applications (Layer 6)
- Procurador-digital: MVP for labor procedural deadlines
- Other applications: concept phase

## What Is Being Consolidated

Current priority work:
- Hard negative mining for BETO (break MRR plateau)
- Review graph implementation
- Graph-Legal-IR canonical population
- Procurador-digital domain expansion

## What Remains Private

Core repositories remain private during consolidation:
- indexo-retriever-prod
- graph-legal-ir (core)
- lexo-research-lab
- legal-ecosystem
- procurar-digital

## Public Components

This repository serves as the public documentation surface. Future public releases may include:
- Constrained demos (specific domains)
- Open-source components (scrapers, tools)
- Evaluation datasets (goldsets)

## What Is Not Claimed

- Full legal coverage: only labor and environmental domains operational
- Perfect retrieval: MRR at 0.62, not 1.0
- Autonomous legal advice: LexO-Alpha assists, does not replace counsel