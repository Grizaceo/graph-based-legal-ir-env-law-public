# 🎯 Strategic Domains

LexCon does not aim to be a general-purpose search engine. Our goal is to provide **high-precision legal reasoning** in specific fields where ambiguity has high stakes.

---

## 🌳 Environmental Law (Derecho Ambiental)
We map the intersection between normative requirements and administrative resolutions.
- **Focus**: SMA (Superintendencia del Medio Ambiente) rulings and SEA (Servicio de Evaluación Ambiental) processes.
- **Data Goal**: Connecting environmental standards to specific case precedents in the environmental courts.

## 💼 Labor Law (Derecho Laboral)
The most active domain in terms of volume.
- **Focus**: *Tutela de Derechos Fundamentales* and *Despido Injustificado*.
- **Data Goal**: Creating a comprehensive graph of DT (Dirección del Trabajo) administrative rulings and their application by Labor Courts.

## 🏛️ Citizen Assistance (Acceso a la Justicia)
Translating technical legal complexity into actionable information.
- **Focus**: Early-stage orientation for common legal conflicts.
- **Data Goal**: Ensuring the "legal orientation" is always consistent with the latest Supreme Court trends (Sentencias Unificadoras).

---

## 🏗️ How we Scale to a New Domain
When we decide to open a new domain (e.g., Family Law or Tax Law), the process is as follows:

1.  **Source Identification**: Define the endpoints for scraping (usually PJUD + Regulatory Agency).
2.  **Canonical Sampling**: Select high-value docs to create a domain-specific goldset.
3.  **Prompt Engineering**: Update the Researcher/Judge subagents with domain-specific heuristics.
4.  **Review Sprint**: A focused effort to approve at least 500 relations into the Canonical Graph.

---

## 📊 Current Coverage (April 2026)
| Domain | Docs in Vault | Graph Status | Application |
| :--- | :--- | :--- | :--- |
| **Labor** | 1,200+ | Production | Procurador / Lexito |
| **Environmental** | 850+ | Beta | Internal Review |
| **Procedural** | 500+ | Production | Procurador |
| **Constitutional**| 300+ | Research | - |
