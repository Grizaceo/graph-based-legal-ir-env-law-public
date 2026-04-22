# 🌐 The LexCon Ecosystem

The LexCon Ecosystem is a decentralized set of tools designed to solve the "Trust Gap" in legal AI. By separating data acquisition, validation, and reasoning into clear layers, we ensure that every response is grounded in verifiable Chilean Law.

---

## 🛠️ Component Breakdown

### 📂 Layer 0-1: Data & Retrieval
- **n8n-judicial**: A set of automated workflows that monitor the PJUD, DT, and SUSESO portals.
- **IndexO**: A high-performance retrieval engine. It handles tokenization, embedding generation (768 dimensions), and similarity search across the ~3,500 document vault.

### 👥 Layer 2-3: The Trust Layers
- **Legal Reviewer**: A web interface for lawyers to label documents and validate extracted relations.
- **Review Graph**: This layer maintains the "Suggested" vs "Canonical" distinction. It handles the lifecycle of knowledge (DRAFT → FROZEN → APPROVED).

### 🤖 Layer 4-5: Reasoning Intelligence
- **LexO-Alpha**: The orchestrator agent. It decomposes legal queries into research tasks and coordinates subagents.
- **Subagent Fleet**: 9 specialized personas (Researcher, Procurador, Judge, Case Designer, etc.) each with its own focus and logic.

### 📱 Layer 6: End-User Applications
- **Lexito**: Simplified assistant for citizens to understand their rights in labor or environmental conflicts.
- **Procurador-digital**: A dedicated tool for managing procedural deadlines (plazos) based on the CPC and specialized laws.
- **Case Writer**: An LLM-powered editor that helps draft legal documents using the evidence from the LKG.

---

## 🏔️ Strategy: Domain-by-Domain
Instead of a "Horizontal" approach (trying to know all law at once), LexCon follows a **Vertical "Deep Dive" Strategy**:

1.  **Labor Law**: Focused on the nuances of Tutela and Despido.
2.  **Environmental Law**: Focused on Administrative Law and SEA resolutions.
3.  **Procedural Law**: Focused on civil and labor procedure deadlines.

---

## 📈 Scalability
The ecosystem is designed to be **provider-agnostic**. While we currently use specialized models like GPT-4o, Claude 3.5, and fine-tuned BETOs, the architecture allows for swapping layers or models as technology evolves without losing the underlying validated knowledge graph.
