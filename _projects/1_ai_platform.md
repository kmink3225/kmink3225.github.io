---
layout: page
title: Enterprise Multi-Agent RAG Platform
description: A company-wide knowledge platform built on multiple cooperating LLM agents — grounded, cited, and continuously evaluated.
img: assets/img/projects/card_01_ai-agent-platform_en.svg
importance: 1
category: work
related_publications: false
mermaid:
  enabled: true
  zoomable: false
---

{% include lang_toggle.liquid active='en' ko='/ko/projects/1_ai_platform/' %}

> Architecture and methodology are described at a high level; production code and internal data are proprietary.

**Role:** Technical Lead / Architect &nbsp;·&nbsp; **Period:** 2025.11 – Present &nbsp;·&nbsp; **Stack:** Python, LangChain, LangGraph, Azure OpenAI, Azure AI Search, FastAPI, React

I architected an enterprise, domain-specific **multi-agent RAG platform** end-to-end, taking it from a single-agent pilot to a company-wide initiative — the program grew out of the success of the earlier [data-standardization system](/projects/2_data_standardization/), promoted from a single-agent plan into a multi-agent flagship project. The platform turns fragmented internal knowledge into a queryable, cited assistant, and comprises several cooperating sub-agents — a **knowledge QnA assistant**, a **data-standardization assistant**, and a **code-analysis agent** — over shared Azure infrastructure. It is live with **~30 practitioners** in the initial rollout and expanding company-wide; two of the three agents shipped **two months ahead of target**.

{% include figure.liquid loading="eager" path="assets/img/projects/poster_01_ai-agent-platform_en.png" class="img-fluid rounded z-depth-1" zoomable=true alt="Enterprise Multi-Agent RAG Platform — project poster" %}

### The three agents

<style>
.ag-tabs { margin: 1rem 0 1.5rem; }
.ag-tabs > input { position: absolute; opacity: 0; pointer-events: none; }
.ag-bar { display: flex; flex-wrap: wrap; gap: .25rem; border-bottom: 1px solid var(--global-divider-color); margin-bottom: 1rem; }
.ag-bar label { padding: .45rem .9rem; cursor: pointer; font-size: .9rem; font-weight: 500; color: var(--global-text-color-light); border-bottom: 2px solid transparent; margin-bottom: -1px; }
.ag-bar label:hover { color: var(--global-text-color); }
.ag-panel { display: none; }
#ag-qna:checked ~ .ag-bar label[for="ag-qna"],
#ag-std:checked ~ .ag-bar label[for="ag-std"],
#ag-code:checked ~ .ag-bar label[for="ag-code"] { color: var(--global-text-color); font-weight: 600; border-bottom-color: var(--global-theme-color); }
#ag-qna:focus-visible ~ .ag-bar label[for="ag-qna"],
#ag-std:focus-visible ~ .ag-bar label[for="ag-std"],
#ag-code:focus-visible ~ .ag-bar label[for="ag-code"] { outline: 2px solid var(--global-theme-color); outline-offset: 2px; }
#ag-qna:checked ~ #ag-panel-qna,
#ag-std:checked ~ #ag-panel-std,
#ag-code:checked ~ #ag-panel-code { display: block; }
.ag-flow { display: flex; flex-wrap: wrap; align-items: center; gap: .35rem; margin: .9rem 0; }
.ag-flow .s { border: 1px solid var(--global-divider-color); background: var(--global-card-bg-color); border-radius: 999px; padding: .22rem .7rem; font-size: .78rem; line-height: 1.35; color: var(--global-text-color); }
.ag-flow .a { color: var(--global-text-color-light); font-size: .8rem; }
.ag-kpis { display: grid; grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); gap: .6rem; margin: 1rem 0; }
.ag-kpi { border: 1px solid var(--global-divider-color); background: var(--global-card-bg-color); border-radius: 8px; padding: .65rem .8rem; }
.ag-kpi .l { font-size: .75rem; line-height: 1.3; color: var(--global-text-color-light); }
.ag-kpi .v { font-size: 1.3rem; font-weight: 600; line-height: 1.25; color: var(--global-text-color); margin-top: .1rem; }
.ag-kpi .d { font-size: .72rem; line-height: 1.3; color: var(--global-text-color-light); margin-top: .1rem; }
.ag-cost { max-width: 560px; margin: 1rem 0 .25rem; }
.ag-cost .r { display: grid; grid-template-columns: minmax(8em, 12em) 1fr 3.6em; align-items: center; gap: .55rem; margin: .4rem 0; }
.ag-cost .n { font-size: .78rem; color: var(--global-text-color); text-align: right; line-height: 1.3; }
.ag-cost .b { height: 14px; border-radius: 0 4px 4px 0; }
.ag-cost .b.base { width: 100%; background: var(--global-text-color-light); }
.ag-cost .b.acc { width: 5.8%; min-width: 4px; background: var(--global-theme-color); }
.ag-cost .v { font-size: .78rem; font-weight: 600; color: var(--global-text-color); font-variant-numeric: tabular-nums; }
.ag-cap { display: block; font-size: .74rem; color: var(--global-text-color-light); margin-top: .1rem; }
@media print {
  .ag-panel { display: block !important; }
  .ag-bar { display: none; }
}
</style>

<div class="ag-tabs">
  <input type="radio" name="ag-tabs" id="ag-qna" checked>
  <input type="radio" name="ag-tabs" id="ag-std">
  <input type="radio" name="ag-tabs" id="ag-code">
  <nav class="ag-bar" aria-label="Platform agents">
    <label for="ag-qna">Knowledge QnA</label>
    <label for="ag-std">Data standardization</label>
    <label for="ag-code">Code analysis</label>
  </nav>

  <section class="ag-panel" id="ag-panel-qna">
    <p><strong>Knowledge QnA chatbot</strong> — a 9 sub-agent <strong>Self-RAG / CRAG</strong> loop with token streaming and source citation. Across a <strong>151-query</strong> operational evaluation it passed <strong>all 10 operational metrics</strong>; a 50-question, 4-model <strong>LLM-as-judge</strong> evaluation scored <strong>5.0 / 5.0</strong> on factuality and reasoning (gpt-4.1).</p>
    <div class="ag-flow">
      <span class="s">User query</span><span class="a" aria-hidden="true">→</span>
      <span class="s">Hybrid retrieval</span><span class="a" aria-hidden="true">→</span>
      <span class="s">Self-RAG / CRAG grading loop</span><span class="a" aria-hidden="true">→</span>
      <span class="s">Cited, streamed answer</span><span class="a" aria-hidden="true">→</span>
      <span class="s">LLM-as-judge scoring</span>
    </div>
    <div class="ag-kpis">
      <div class="ag-kpi"><div class="l">User satisfaction</div><div class="v">~98%</div></div>
      <div class="ag-kpi"><div class="l">Avg response</div><div class="v">4.66s</div></div>
      <div class="ag-kpi"><div class="l">Citation rate</div><div class="v">96.9%</div></div>
      <div class="ag-kpi"><div class="l">RAG retrieval success</div><div class="v">95.6%</div></div>
      <div class="ag-kpi"><div class="l">System success</div><div class="v">100%</div></div>
      <div class="ag-kpi"><div class="l">LLM-judge factuality · reasoning</div><div class="v">5.0/5.0</div></div>
    </div>
  </section>

  <section class="ag-panel" id="ag-panel-std">
    <p><strong>Data-standardization assistant</strong> — a Rule + ALBERT classifier + RAG hybrid (LangGraph Reflexion loop) that auto-recommends three metadata fields; the productionized successor of the earlier <a href="/projects/2_data_standardization/">data-standardization system</a>. Across a <strong>101-query</strong> evaluation it passed <strong>all 10 operational metrics</strong>.</p>
    <div class="ag-flow">
      <span class="s">Metadata query</span><span class="a" aria-hidden="true">→</span>
      <span class="s">Rule engine · ALBERT classifier · RAG lookup</span><span class="a" aria-hidden="true">→</span>
      <span class="s">Merged recommendation + confidence</span><span class="a" aria-hidden="true">→</span>
      <span class="s">LangGraph Reflexion check</span>
    </div>
    <div class="ag-kpis">
      <div class="ag-kpi"><div class="l">User satisfaction</div><div class="v">90.4%</div></div>
      <div class="ag-kpi"><div class="l">Avg response</div><div class="v">3.75s</div></div>
      <div class="ag-kpi"><div class="l">Fallback rate</div><div class="v">0%</div></div>
      <div class="ag-kpi"><div class="l">Operational metrics passed</div><div class="v">10/10</div></div>
    </div>
  </section>

  <section class="ag-panel" id="ag-panel-code">
    <p><strong>Code-analysis agent</strong> — grounded a ~400K-line Python codebase (32 repos, 1,453 files) into <strong>40K AST facts</strong>, a code graph (<strong>11,729 nodes / 38,783 edges</strong>), and a 42K search index. A 3-architecture benchmark — <strong>raw Claude Code vs. Claude Code + a metadata/skill harness vs. self-built orchestration</strong>, 9 variants — put the self-built, determinism-first grounded pipeline on a mini-tier model (GPT-5.4-mini) <strong>1st (composite 0.977)</strong>, validated with paired t-test / McNemar / Cohen's d / bootstrap CI over a 6-metric composite; now nearing production deployment. Full comparison in the case study below.</p>
    <div class="ag-flow">
      <span class="s">~400K-line codebase</span><span class="a" aria-hidden="true">→</span>
      <span class="s">40K AST facts · code graph · 42K index</span><span class="a" aria-hidden="true">→</span>
      <span class="s">Grounded pipeline on GPT-5.4-mini</span><span class="a" aria-hidden="true">→</span>
      <span class="s">Answer with provenance</span>
    </div>
    <div class="ag-kpis">
      <div class="ag-kpi"><div class="l">AST facts</div><div class="v">40K</div></div>
      <div class="ag-kpi"><div class="l">Code graph (nodes / edges)</div><div class="v">11.7K / 38.8K</div></div>
      <div class="ag-kpi"><div class="l">Benchmark composite</div><div class="v">0.977</div><div class="d">1st of 9 variants</div></div>
      <div class="ag-kpi"><div class="l">Cost per query</div><div class="v">$0.076</div><div class="d">up to ~17× lower</div></div>
    </div>
    <div class="ag-cost">
      <div class="r">
        <span class="n">Costliest CLI variant</span>
        <div><div class="b base"></div></div>
        <span class="v">$1.32</span>
      </div>
      <div class="r">
        <span class="n">Self-built orchestration</span>
        <div><div class="b acc"></div></div>
        <span class="v">$0.076</span>
      </div>
      <span class="ag-cap">Cost per query on the same 51-question eval set — up to ~17× lower.</span>
    </div>
  </section>
</div>

### Platform foundation

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

### Per-agent architecture

The three agents share the RAG foundation but run different orchestration strategies: the QnA assistant is corrective + Self-RAG, the standardization assistant pins a deterministic rule engine ahead of RAG to minimize autonomous judgment, and the code-analysis agent stacks Graph RAG under Agentic RAG.

**Knowledge QnA — corrective + Self-RAG**

```mermaid
flowchart LR
    Q[User query] --> R[Hybrid retrieval<br/>BM25 + vector]
    R --> G{Relevance grade}
    G -- fail --> RW[Rewrite /<br/>re-retrieve]
    RW --> R
    G -- pass --> A[Generate + cite]
    A --> SC{Self-check}
    SC -- revise --> A
    SC -- ok --> OUT[Streamed, cited answer]
```

**Data standardization — Rule + ALBERT + RAG hybrid**

```mermaid
flowchart LR
    M[Metadata field] --> RULE[Rule engine<br/>300+ rules, abbrev dict]
    M --> CLF[ALBERT domain classifier]
    M --> RAG[RAG recommender]
    RULE --> MRG[Merge + confidence]
    CLF --> MRG
    RAG --> MRG
    MRG --> AUD{Domain auditor<br/>LangGraph corrective}
    AUD -- revise --> RAG
    AUD -- ok --> OUT[3 metadata recommendations]
```

**Code analysis — 2-layer RAG, Graph then Agentic**

```mermaid
flowchart LR
    CB[~400K-line codebase] --> IDX[40K AST facts<br/>code graph, 11.7K nodes]
    IDX --> L1[Layer 1: Graph RAG<br/>code relations]
    L1 --> L2[Layer 2: Agentic RAG<br/>autonomous exploration]
    L2 --> OUT[Grounded answer<br/>with provenance]
```

### Case study — self-built orchestration vs. Claude Code

**Problem.** A general-purpose CLI agent (Claude Code) could already answer internal questions, but its cost-per-query profile did not scale to company-wide adoption, and "it feels better" is not an argument a platform decision can rest on.

**What changed.** I benchmarked **three architectures** head-to-head — raw Claude Code, Claude Code wrapped in a metadata/skill harness, and a dedicated self-built orchestration around the RAG pipeline that keeps the control plane in-house — across **9 variants** (including the latest Claude Sonnet 5) on a 51-question eval set with a 6-metric composite, treating the comparison as a designed experiment rather than a demo.

| Rank | Architecture | Model (channel) | Composite | Latency (s) | Cost ($) |
|---|---|---|---|---|---|
| 1 | **Self-built orchestration** | GPT-5.4-mini (API) | **0.977** | 11.6 | **0.076** |
| 2 | Claude Code + meta/skills | Sonnet 4.6 (sub) | 0.875 | 161.6 | 0.66 |
| 3 | Claude Code (raw) | Opus 4.8 (sub) | 0.840 | 110.7 | 0.76 |
| 4 | Claude Code + meta/skills | Haiku 4.5 (sub) | 0.836 | 64.2 | 0.19 |
| 5 | Claude Code (raw) | Sonnet 4.6 (sub) | 0.828 | 95.8 | 0.44 |
| 6 | Claude Code + meta/skills | Opus 4.8 (sub) | 0.823 | 169.2 | 1.32 |
| 7 | Claude Code (raw) | Sonnet 5 (sub) | 0.815 | 108.8 | 0.50 |
| 8 | Claude Code (raw) | Sonnet 5 (int) | 0.800 | — | — |
| 9 | Claude Code (raw) | Haiku 4.5 (sub) | 0.758 | 51.8 | 0.136 |

*Composite = weighted sum of accuracy, no-hallucination, completeness, structure-traceability, relevance, and citation. Latency and cost are per query; the response-collection channel is in parentheses — `sub` = subscription CLI, `API` = direct API, `int` = interactive (efficiency not measured). The self-built orchestration answers in a single grounded API call, so it is both the cheapest and the fastest while topping the composite.*

**Result.** The self-built, determinism-first orchestration won overall — a grounded mini-tier model leading frontier CLI agents on answer quality at up to ~17× lower cost per query, with the gap established by paired t-test · McNemar · Cohen's d · bootstrap CI rather than impression — the evidence that justified moving from a single-agent pilot to a company-wide rollout. The winning pipeline is now nearing production deployment.

### Why it matters

A self-built harness keeps the control plane in-house: vendor flexibility, cost control, and knowledge captured as a durable asset rather than rented from a single provider. I made this case beyond my own team, too: across two Microsoft workshops I led the technical discussion and persuaded a Microsoft architect and seven engineers of the self-built orchestration approach over a general-purpose Copilot CLI.
