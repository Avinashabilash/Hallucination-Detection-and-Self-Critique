# 📘 Hallucination Detection and Reduction in LLMs Using RAG and Self-Critique

This repository contains a ready-to-run **git-friendly** project structure, a clear flowchart (Mermaid) visualizing the pipeline, explanatory images/ASCII, and runnable code snippets to get started quickly.

---

## 📌 Project Summary (1-sentence)

A lightweight framework to detect, score, and reduce hallucinations in LLMs by comparing baseline generation, Retrieval-Augmented Generation (RAG), and a self-critique correction stage.

---

## 🔄 Flowchart (Mermaid)

```mermaid
flowchart TD
  A[User Question] --> B[Retriever (FAISS + MiniLM)]
  B --> C[Top-k Evidence]
  C --> D[Prompt Constructor (RAG)]
  D --> E[Answer Generator (Flan-T5)]
  E --> F[Self-Critique Module]
  F --> G[Hallucination Detector & Scorer]
  G --> H[Results.csv & Visualizations]
  E --> I[Baseline Generator (no retrieval)]
  I --> G
  style A fill:#f9f,stroke:#333,stroke-width:1px
  style H fill:#bbf,stroke:#333,stroke-width:1px
```
## Architecture Breakdown

Retriever Layer: Uses FAISS + MiniLM to fetch the top-k meaningful evidence.

Generator Layer: Flan-T5 produces:

Baseline answer (no context)

RAG answer (context injected)

Critique Layer: The model evaluates its own output.

## Evaluation Layer: Detects unsupported claims.

Output Layer: Generates CSV logs, ready for analysis.

Evaluation Metrics (Planned/Future Work)

Faithfulness Score: Measures evidence alignment.

Semantic Similarity: Embedding cosine similarity.

Contradiction Detection: Using NLI models.

Hallucination Percentage: Baseline vs RAG comparison.
