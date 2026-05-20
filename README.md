AI-Hallucination-Fact-Checking-Factual-Verification-Layer-

A transparent, claim-level verification framework designed to mitigate LLM hallucinations. This system moves AI-generated content from probabilistic "plausible" text to verifiable, evidence-backed reasoning by decomposing responses into atomic claims and cross-referencing them against trusted knowledge bases.

## 🧠 Core Methodology
The framework implements a rigorous verification pipeline:
* **Atomic Decomposition:** Deconstructs complex LLM responses into independent, testable facts.
* **Evidence Retrieval:** Executes targeted semantic search across source documentation to ground each claim.
* **Verification & Scoring:** Utilizes NLI (Natural Language Inference) models to validate claim-source alignment, assigning a status of **Supported**, **Uncertain**, or **Unsupported**.
* **Aggregate Trust Metrics:** Computes a transparent confidence score based on the proportion of verified claims, providing users with a quantifiable "trust index."

## 🏗️ System Architecture
The pipeline follows a modular **RAG (Retrieval-Augmented Generation)** architecture:
1. **Generation Module:** LLM-based output generation.
2. **Claim Extractor:** LLM-driven parsing to generate JSON-structured atomic claims.
3. **Retrieval Module:** Vector-based search for relevant source passages.
4. **Verification Engine:** Embedding-based similarity and NLI verification scoring.
5. **Dashboard Layer:** A [Streamlit](https://streamlit.io/) interface displaying real-time claim status and evidence linking.

## 📈 Impact
This system addresses the primary barrier to enterprise LLM adoption: **the lack of verifiable accuracy**. By creating an auditable trace from final answer to source document, it enables high-stakes applications in technical documentation, legal research, and corporate knowledge management.
## 🧪 Demo Output Example
*Input: "Alexander Graham Bell invented the telephone in 1876."*

| Claim | Status | Evidence |
| :--- | :--- | :--- |
| Alexander Graham Bell invented the telephone | ✅ Supported | [Source: History_Docs.pdf, p.14] |
| The invention occurred in 1876 | ✅ Supported | [Source: History_Docs.pdf, p.15] |
| It was funded by the US Navy | ❌ Unsupported | N/A |
