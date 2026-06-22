---
layout: page
title: CV
permalink: /cv/
nav: true
nav_order: 5
description: Curriculum vitae — Kwangmin Kim, AI Engineer / Data Scientist.
toc:
  sidebar: left
---

<div style="text-align: right; margin-bottom: 1rem;"><strong>English</strong> · <a href="/ko/cv/">한국어</a></div>

**Kwangmin Kim (김광민)** · AI Engineer / Data Scientist · Seoul, South Korea
[kmink3225@gmail.com](mailto:kmink3225@gmail.com) · [GitHub](https://github.com/kmink3225) · [LinkedIn](https://www.linkedin.com/in/kwangmin-kim-a5241b200/)

## Summary

AI Engineer / Data Scientist with 7+ years of experience architecting and building enterprise AI platforms (RAG, LLM agents, NLP) end-to-end, backed by statistically rigorous evaluation. Specialties: LLM agents, RAG/Graph RAG, deep learning / NLP, machine learning, experiment design, and statistical analysis.

## Experience

### Seegene — Data Scientist / AI Engineer

*2020.12 – Present · South Korea*

Technical lead / architect on a company-wide multi-agent platform; architecting enterprise AI agent / RAG platforms and the statistical evaluation systems behind them. Previously led ML and statistical modeling for diagnostics.

- Architected a domain-specific **multi-agent RAG knowledge platform** end-to-end and led it from a single-agent pilot to a company-wide initiative (~30 initial users, expanding company-wide).
- Designed a **knowledge QnA chatbot** (9 sub-agent **Self-RAG/CRAG** loop, token streaming, source citation): ~98% user satisfaction, 4.66s avg response, 96.9% citation rate, 100% system success; 5.0/5.0 factuality & reasoning on a 4-model LLM-as-judge evaluation.
- Built a **self-developed agent orchestration** that benchmarked **up to ~17× lower cost per query** vs. a general-purpose CLI (paired t-test / McNemar / bootstrap CI on a 6-metric composite).
- Delivered an **NLP-based data standardization system**: validation time **8h → 0.73s (99%↓)**, metadata consistency 8.4% → 98.7%; an 8-model classifier benchmark (14 classes, 95% CI, McNemar+Holm) selected KLUE-RoBERTa at 96.88% and proved a 671K-param BiLSTM statistically on par with a 110M model.
- Redesigned a hard-coded PCR signal baseline algorithm into a **data-driven model**, cutting the false-negative rate **0.47% → 0.04% (91.49%↓)**.
- Automated diagnostic-equipment QC with a **two-stage LSTM + 10 metrics** over 61,248 signals, cutting QC time ~93% (≈13× annual operating-cost reduction) — R&D President's Award.
- Established a model evaluation & MLOps baseline (LLM-as-judge auto-scoring + architecture A/B benchmarking + metric logging); mentored 20+ engineers across IT/BT.

### Columbia University Irving Medical Center — Taub Institute · Statistical Research Assistant

*2018.12 – 2020.05 · New York, US*

Large-scale multi-omics analysis for Alzheimer's disease biomarker discovery.

- Integrated genomic, metabolomic, and clinical data to surface **13 key biomarkers (p<0.01)** from ~3,000 metabolites; uncovered a confounder missed for eight months.
- Handled 146 samples × 3,000 high-dimensional variables; compared 10+ ML algorithms and selected sPLS (84% accuracy with interpretability); built 20-year onset-risk models with Cox hazard / GEE.

## Education

- **M.S. Biostatistics**, Columbia University (2017–2019) — Chair's Award
- **B.A. Mathematics**, Baruch College, CUNY (2015–2017)
- **B.S. Biochemistry**, Kangwon National University (2006–2012) — Valedictorian, Dean's Award

## Skills

- **LLM Agent / GenAI** — RAG, Agentic RAG, Graph RAG, Self-RAG/CRAG, LangChain, LangGraph, Azure OpenAI, Azure AI Search, OpenAI/Claude API, Prompt Engineering
- **NLP / Deep Learning** — KLUE-RoBERTa, KoBERT, ALBERT, BiLSTM/LSTM, Hugging Face Transformers, PyTorch, KiwiPiePy/KoNLPy
- **ML / Statistics** — scikit-learn, HDBSCAN, regression/survival analysis, time series, causal inference (A/B test), experiment design
- **Data / Backend Engineering** — Python, R, SQL (PostgreSQL), SAS, FastAPI, Streamlit, Apache Airflow, Parquet, AST, Docker, Azure DevOps

## Awards & Patents

- **7 patents filed** (first inventor on 4) — Ct-based customized treatment; medical-platform subscription system; diagnostic-equipment noise-test automation; medical-equipment noise-level algorithm (first inventor); molecular-diagnostics prediction model, etc. (co-inventor). Seegene, 2021–2022.
- **President's Award** (R&D), Seegene, 2021
- **Chair's Award** — Graduation Practicum Research Competition, Columbia Biostatistics, 2019

## Certificates

- Microsoft Azure — DP-203 (Data Engineering), DP-100 (Data Science), DP-300 (Database), 2025
- SAS Certified Base Programmer, 2018

## Languages

- Korean (native) · English (fluent)
