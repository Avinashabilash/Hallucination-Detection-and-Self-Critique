# 📘 Hallucination Detection and Reduction in LLMs Using RAG and Self-Critique

This repository contains a ready-to-run **git-friendly** project structure, a clear flowchart (Mermaid) visualizing the pipeline, explanatory images/ASCII, and runnable code snippets to get started quickly.

---

## 📌 Project Summary (1-sentence)

A lightweight framework to detect, score, and reduce hallucinations in LLMs by comparing baseline generation, Retrieval-Augmented Generation (RAG), and a self-critique correction stage.

---

## Architecture Breakdown

Retriever Layer: Uses FAISS + MiniLM to fetch the top-k meaningful evidence.

Generator Layer: Flan-T5 produces:

Baseline answer (no context)

RAG answer (context injected)

Critique Layer: The model evaluates its own output.

## 🔄 Flowchart (Mermaid)

```mermaid
flowchart TD
    A[User Question] --> B[Retriever using FAISS and MiniLM]
    B --> C[Top k Evidence]
    C --> D[RAG Prompt Builder]
    D --> E[Answer Generator Flan T5]
    E --> F[Self Critique Module]
    F --> G[Hallucination Scorer]
    G --> H[Results CSV and Visualization]
    E --> I[Baseline Generator]
    I --> G
