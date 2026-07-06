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
  zoomable: false
---

<div style="text-align: right; margin-bottom: 1rem;"><strong>English</strong> · <a href="/ko/projects/1_ai_platform/">한국어</a></div>

> Architecture and methodology are described at a high level; production code and internal data are proprietary.

**Role:** Technical Lead / Architect &nbsp;·&nbsp; **Period:** 2025.11 – Present &nbsp;·&nbsp; **Stack:** Python, LangChain, LangGraph, Azure OpenAI, Azure AI Search, FastAPI, React

I architected an enterprise, domain-specific **multi-agent RAG platform** end-to-end, taking it from a single-agent pilot to a company-wide initiative — the program grew out of the success of the earlier [data-standardization system](/projects/2_data_standardization/), promoted from a single-agent plan into a multi-agent flagship project. The platform turns fragmented internal knowledge into a queryable, cited assistant, and comprises several cooperating sub-agents — a **knowledge QnA assistant**, a **data-standardization assistant**, and a **code-analysis agent** — over shared Azure infrastructure. It is live with **~30 practitioners** in the initial rollout and expanding company-wide; two of the three agents shipped **two months ahead of target**.

### Highlights

- **Knowledge QnA chatbot** — a 9 sub-agent **Self-RAG / CRAG** loop with token streaming and source citation. Across a **151-query** operational evaluation it passed all 10 operational metrics: ~98% user satisfaction, **4.66s** average response, 96.9% citation rate, 95.6% RAG retrieval success, 100% system success. A 50-question, 4-model **LLM-as-judge** evaluation scored 5.0/5.0 on factuality and reasoning (gpt-4.1).
- **Data-standardization assistant** — a Rule + ALBERT classifier + RAG hybrid (LangGraph Reflexion loop) that auto-recommends three metadata fields; the productionized successor of the earlier [data-standardization system](/projects/2_data_standardization/). Across a 101-query evaluation it passed all 10 operational metrics: **90.4%** user satisfaction, 3.75s average response, 0% fallback.
- **Code-analysis agent & 3-architecture benchmark** — grounded a ~400K-line Python codebase (32 repos, 1,453 files) into **40K AST facts**, a code graph (**11,729 nodes / 38,783 edges**), and a 42K search index; benchmarked **raw Claude Code vs. Claude Code + a metadata/skill harness vs. self-built orchestration** (11 variants) — the self-built orchestration, a determinism-first grounded pipeline on a mini-tier model (GPT-5.4-mini), ranked **1st (composite 0.977)** at **up to ~17× lower cost per query**, validated with paired t-test / McNemar / Cohen's d / bootstrap CI over a 6-metric composite; now nearing production deployment.
- **RAG pipeline** — Parent-Child + contextual chunking, hybrid search (BM25 + vector), child→parent mapping, and reranking to suppress hallucination; a LangChain → LangGraph → Agentic 3-stage orchestration roadmap.
- **Evaluation & MLOps** — LLM-as-judge auto-scoring (factuality, reasoning, out-of-scope, multi-turn) + architecture A/B benchmarking + metric logging for operations, cutting estimated cloud operating cost by **~32%**.

### Architecture

The platform's sub-agents share a common foundation — a hybrid (BM25 + vector) RAG index with parent-child + contextual chunking and reranking — and a common evaluation loop. The knowledge QnA assistant runs a 9 sub-agent Self-RAG / CRAG loop with token streaming and citation; the data-standardization and code-analysis agents reuse the same grounding and orchestration. An LLM-as-judge stage scores every interaction and feeds quality signals back to each agent.

```mermaid
flowchart TB
    DOCS[Internal knowledge] --> IDX[(Hybrid RAG index<br/>BM25 + vector, parent-child)]
    Q[User query] --> ORCH[Orchestration / control plane]
    IDX --> ORCH
    ORCH --> A1[Knowledge QnA assistant<br/>9 sub-agent Self-RAG / CRAG]
    ORCH --> A2[Data-standardization assistant<br/>Rule + classifier + RAG]
    ORCH --> A3[Code-analysis agent<br/>self-built orchestration]
    A1 --> OUT[Grounded, cited output]
    A2 --> OUT
    A3 --> OUT
    OUT --> EVAL[LLM-as-judge evaluation]
    EVAL -. quality feedback .-> ORCH
```

Orchestration follows a deliberate LangChain → LangGraph → Agentic roadmap, so the control plane grows in capability without locking into a single framework.

### Case study — self-built orchestration vs. Claude Code

**Problem.** A general-purpose CLI agent (Claude Code) could already answer internal questions, but its cost-per-query profile did not scale to company-wide adoption, and "it feels better" is not an argument a platform decision can rest on.

**What changed.** I benchmarked **three architectures** head-to-head — raw Claude Code, Claude Code wrapped in a metadata/skill harness, and a dedicated self-built orchestration around the RAG pipeline that keeps the control plane in-house — across **11 variants** (including the latest Claude Sonnet 5 both raw and harnessed) on a 51-question eval set with a 6-metric composite, treating the comparison as a designed experiment rather than a demo.

| Architecture | Outcome |
|---|---|
| Raw Claude Code | capable baseline; cost per query does not scale (costliest variant $1.32) |
| Claude Code + metadata/skill harness | improved answer usefulness over raw on the same model — cross-validated by blind practitioner review |
| Self-built orchestration | **composite 0.977 — 1st of 11 variants** · 11.6s · **$0.076/query (up to ~17× lower)** — determinism-first grounding on a mini-tier model (GPT-5.4-mini) |

**Result.** The self-built, determinism-first orchestration won overall — a grounded mini-tier model leading frontier CLI agents on answer quality at up to ~17× lower cost per query, with the gap established by paired t-test · McNemar · Cohen's d · bootstrap CI rather than impression — the evidence that justified moving from a single-agent pilot to a company-wide rollout. The winning pipeline is now nearing production deployment.

### Why it matters

A self-built harness keeps the control plane in-house: vendor flexibility, cost control, and knowledge captured as a durable asset rather than rented from a single provider. I made this case beyond my own team, too: across two Microsoft workshops I led the technical discussion and persuaded a Microsoft architect and seven engineers of the self-built orchestration approach over a general-purpose Copilot CLI.
