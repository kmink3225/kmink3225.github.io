---
layout: page
title: Enterprise Multi-Agent RAG Platform
description: A company-wide knowledge platform built on multiple cooperating LLM agents — grounded, cited, and continuously evaluated.
img: assets/img/1.jpg
importance: 1
category: work
related_publications: false
mermaid:
  enabled: true
  zoomable: true
---

> Architecture and methodology are described at a high level; production code and internal data are proprietary.

**Role:** Technical Lead / Architect &nbsp;·&nbsp; **Stack:** Python, LangChain, LangGraph, Azure OpenAI, Azure AI Search, FastAPI

I architected an enterprise, domain-specific **multi-agent RAG platform** end-to-end, taking it from a single-agent pilot to a company-wide initiative. The platform turns fragmented internal knowledge into a queryable, cited assistant.

### Highlights

- **Knowledge QnA chatbot** — a 9 sub-agent **Self-RAG / CRAG** loop with token streaming and source citation. On a 151-query suite it passed all 10 operational metrics: ~98% user satisfaction, **4.66s** average response, 96.9% citation rate, 100% system success. A 50-question, 4-model **LLM-as-judge** evaluation scored 5.0/5.0 on factuality and reasoning.
- **Self-built orchestration vs. general-purpose CLI** — benchmarked **up to ~17× lower cost per query** at the top-performing configuration, validated with paired t-test / McNemar / Cohen's d / bootstrap CI over a 6-metric composite.
- **RAG pipeline** — Parent-Child + contextual chunking, hybrid search (BM25 + vector), child→parent mapping, and reranking to suppress hallucination; a LangChain → LangGraph → Agentic 3-stage orchestration roadmap.
- **Evaluation & MLOps** — LLM-as-judge auto-scoring (factuality, reasoning, out-of-scope, multi-turn) + architecture A/B benchmarking + metric logging for operations.

### Architecture

The platform is a retrieval-grounded, continuously-evaluated agent loop. Documents are chunked with parent-child + contextual strategies into a hybrid (BM25 + vector) index; retrieval reranks and maps children back to parents before a 9 sub-agent Self-RAG / CRAG loop composes a cited answer. An LLM-as-judge stage scores every interaction and feeds quality signals back into the loop.

```mermaid
flowchart TB
    DOC[Internal documents] --> CHUNK[Parent-Child + contextual chunking]
    CHUNK --> IDX[(Hybrid index<br/>BM25 + vector)]
    Q[User query] --> R[Retrieval]
    IDX --> R
    R --> MAP[Child-to-parent mapping + rerank]
    MAP --> LOOP[9 sub-agent<br/>Self-RAG / CRAG loop]
    LOOP --> ANS[Cited answer<br/>+ token streaming]
    LOOP --> EVAL[LLM-as-judge evaluation<br/>factuality · reasoning · out-of-scope · multi-turn]
    EVAL -. quality feedback .-> LOOP
```

Orchestration follows a deliberate LangChain → LangGraph → Agentic roadmap, so the control plane grows in capability without locking into a single framework.

### Case study — self-built orchestration vs. a general-purpose CLI

**Problem.** A general-purpose CLI agent could already answer internal questions, but its cost-per-query profile did not scale to company-wide adoption, and "it feels better" is not an argument a platform decision can rest on.

**What changed.** I built a dedicated orchestration harness around the RAG pipeline — keeping the control plane in-house — and benchmarked it head-to-head against the general-purpose CLI on a 6-metric composite, treating the comparison as a designed experiment rather than a demo.

| Dimension | General-purpose CLI | Self-built orchestration |
|---|---|---|
| Cost per query | baseline (1×) | **up to ~17× lower** at the top configuration |
| Decision basis | anecdote | paired t-test · McNemar · Cohen's d · bootstrap CI |

**Result.** Up to ~17× lower cost per query while holding answer quality, with the gap established by statistical tests rather than impression — the evidence that justified moving from a single-agent pilot to a company-wide rollout.

### Why it matters

A self-built harness keeps the control plane in-house: vendor flexibility, cost control, and knowledge captured as a durable asset rather than rented from a single provider.
