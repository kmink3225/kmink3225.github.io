---
layout: page
title: Enterprise Multi-Agent RAG Platform
description: A company-wide knowledge platform built on multiple cooperating LLM agents — grounded, cited, and continuously evaluated.
img: assets/img/1.jpg
importance: 1
category: work
related_publications: false
---

> Architecture and methodology are described at a high level; production code and internal data are proprietary.

**Role:** Technical Lead / Architect &nbsp;·&nbsp; **Stack:** Python, LangChain, LangGraph, Azure OpenAI, Azure AI Search, FastAPI

I architected an enterprise, domain-specific **multi-agent RAG platform** end-to-end, taking it from a single-agent pilot to a company-wide initiative (~30 initial users, expanding company-wide). The platform turns fragmented internal knowledge into a queryable, cited assistant.

### Highlights

- **Knowledge QnA chatbot** — a 9 sub-agent **Self-RAG / CRAG** loop with token streaming and source citation. On a 151-query suite it passed all 10 operational metrics: ~98% user satisfaction, **4.66s** average response, 96.9% citation rate, 100% system success. A 50-question, 4-model **LLM-as-judge** evaluation scored 5.0/5.0 on factuality and reasoning.
- **Self-built orchestration vs. general-purpose CLI** — benchmarked **up to ~17× lower cost per query** at the top-performing configuration, validated with paired t-test / McNemar / Cohen's d / bootstrap CI over a 6-metric composite.
- **RAG pipeline** — Parent-Child + contextual chunking, hybrid search (BM25 + vector), child→parent mapping, and reranking to suppress hallucination; a LangChain → LangGraph → Agentic 3-stage orchestration roadmap.
- **Evaluation & MLOps** — LLM-as-judge auto-scoring (factuality, reasoning, out-of-scope, multi-turn) + architecture A/B benchmarking + metric logging for operations.

### Why it matters

A self-built harness keeps the control plane in-house: vendor flexibility, cost control, and knowledge captured as a durable asset rather than rented from a single provider.
