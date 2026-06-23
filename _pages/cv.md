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

AI Engineer / Data Scientist with 7+ years of experience, architecting and building enterprise AI platforms (RAG, LLM agents, NLP) end-to-end. I built an enterprise **AI-agent knowledge platform** from the architecture up (**~98% user satisfaction**) and delivered a **data standardization system** (validation time cut **99%**) that is now expanding into a company-wide multi-agent platform under my technical lead. My self-built agent orchestration benchmarked **up to ~18× lower cost** than general-purpose models; I also cut diagnostic-equipment QC operating cost **~13×/yr**, alongside statistically rigorous model evaluation and experiment design. I have led multidisciplinary teams (up to ~20) and filed **7 patents (first inventor on 4)**.

**Specialties:** LLM agents, RAG system design/implementation, NLP / deep learning, machine learning, experiment design, statistical analysis, diagnostic algorithms.

## Experience

### Seegene — Data Scientist / AI Engineer

*Diagnosis IT General Research Institute · Data Science / Core Dev Team · 2020.12 – Present · South Korea*

**Enterprise AI-Agent Knowledge Platform** — Technical Lead / AI Architect, 2025.11 – Present

- Led end-to-end architecture of a domain-specific **multi-agent RAG platform** for company-wide data assetization (deployed to working-level staff, expanding company-wide) — three agents (knowledge QnA, data standardization, sequence-recommendation code analysis) on shared Azure infrastructure; scaled a single-agent plan into a multi-agent flagship and delivered two agents **2 months ahead of target**.
- **Knowledge QnA chatbot** — 9 sub-agent **Self-RAG/CRAG** loop with token streaming and source citation over a Parent-Child + hybrid-search (BM25 + vector) RAG pipeline; passed all 10 metrics (**4.66s** avg response, 96.9% citation rate, 100% system success, 95.6% retrieval success), **5.0/5.0** factuality & reasoning (gpt-4.1) on a 4-model LLM-as-judge eval, **~98%** user satisfaction.
- **Data-standardization assistant agent** — Rule + ALBERT classifier + RAG **hybrid engine** (LangGraph Reflexion loop) auto-recommending three metadata types; passed all 10 metrics, **90.4%** satisfaction, 3.75s avg response, 0% fallback.
- **Sequence-recommendation code-analysis agent** — grounded ~400K lines of Python (32 repos, 1,453 files) into **40K AST facts**, a code graph (**11,729 nodes / 38,783 edges**), and a 42K search index; benchmarked three architectures (raw general-purpose CLI vs. metadata+skill harness vs. self-built orchestration; 7 variants) on a 6-metric composite + statistical tests — the harness beat the general CLI on answer usefulness (cross-validated by blind practitioner review), and the **self-built orchestration won overall** (GPT-5.4-mini composite **0.977**, 11.6s, $0.076/query), **~17× cheaper** than the costliest variant; nearing production.
- **Evaluation & MLOps baseline** — LLM-as-judge auto-scoring (factuality / reasoning / out-of-scope / multi-turn) + architecture A/B benchmarking (paired t-test, McNemar, Cohen's d, bootstrap CI) + metric logging; ran **32%** below projected cloud operating cost, with a self-built harness strategy hedging vendor lock-in.
- Drove **two Microsoft workshops**, persuading an **MS architect and 7 engineers** to adopt the self-built orchestration over a general-purpose Copilot CLI.

**NLP-Based Data Standardization System** — Technical Lead (mentored 20+ across IT/BT), 2024.10 – 2025.09

- Defined the metadata-inconsistency problem and led an **NLP + Rule + RAG** standardization system end-to-end; after a successful pilot it went **company-wide** and seeded the follow-on AI-agent platform.
- Outcomes (user survey + ops): validation time **8h → 0.73s (99%↓)**, cross-team inquiries **70 → 4/mo (94.3%↓)**, metadata consistency **8.4% → 98.7%**, completeness **29.6% → 100%**.
- **8-model classifier benchmark** (KLUE-RoBERTa, XLM, KoBERT, ALBERT, mBERT, BiLSTM, DistilKoBERT, e5; 14 classes, 7,698 samples, stratified, 95% CI, McNemar+Holm over 28 pairs) → **KLUE-RoBERTa 96.88%** (top-5 transformers statistically tied).
- **Robustness / 5-way cross-validation** — 5-fold CV showed a **671K-param BiLSTM statistically on par with the 110M KLUE** (96.18%±0.41% vs. 96.35%, p=0.73) at **1.48ms inference** (vs. 12.49ms); suffix ablation (−51%p), a RAG holdout (rejected synthetic-overfit), and a noise floor diagnosed the accuracy ceiling as a data limit.
- **Training-data engineering** — curated 9,168 items from three sources (LLM, rules, RAG) → label normalization, 29 conflicts resolved, 1,466 deduplicated → 7,698; built dictionaries of 582 standard terms and 147 domain mappings.
- **Rule-based naming-standardization engine** (14 rules + physical-name / abbreviation generation); synonym clustering (ko-sroberta-multitask + HDBSCAN, 2,048 → 569 clusters); **pytest (60), GitHub Actions CI, Docker** for reproducible ML.

**Time-Series PCR Signal Baseline-Correction Optimization** — Project PM (DS 3, DE 1), 2024.01 – 2024.09

- Redesigned a hard-coded legacy baseline algorithm into a **mixed-basis data-driven model**, cutting the false-negative rate **0.47% → 0.04% (91.49%↓)**; refactored Matlab → low-level Python with real-time lightweight regression, ranking 1st of 5 competing algorithms on white-noise residual fit.

**FDA-Submission Diagnostic-Algorithm Safety Statistical Analysis** — Project PM (16, multidisciplinary), 2023.05 – 2023.12

- Designed and automated the **statistical V&V pipeline** for FDA software validation, cutting validation time **6 months → 3 weeks (87.5%↓)** at 99.2% statistical confidence; implemented C++-port statistical tests (2-way RM-ANOVA, McNemar, Breslow-Day, Cochran-Mantel-Haenszel), an in-house **Switch Model** ablation, and an Airflow → R + Quarto pipeline generating a 200-page V&V report.

**RT-PCR Diagnostic-Algorithm Reverse Engineering & Statistical Modeling** — Data Scientist (team of 6), 2021.10 – 2023.04

- Reverse-engineered an undocumented legacy Matlab algorithm (10+ stages, 50+ empirical parameters) to **80%** logic/dependency coverage with a C++-port spec; designed an RT-PCR-kinetics logistic-sigmoid composite with joint normal estimation to remove systematic bias.

**PCR-Equipment QC Protocol Design & Performance Grading (A+/A/B/F)** — Project PM (11, multidisciplinary), 2020.12 – 2021.09

- Automated manual Excel QC with a **two-stage LSTM + 10 quality metrics** grading system: QC time **~400h → 28h per 100 units (93%↓)**, **~13× annual operating-cost reduction**; over 2,201 units and **61,248 signals**, 94.5% pass/fail and 82.7% grade accuracy, with PCA/t-SNE/DBSCAN anomaly detection and an R Shiny dashboard — **R&D President's Award**, **2 first-inventor patents**.

### Columbia University Irving Medical Center — Taub Institute · Statistical Research Assistant

*Research on Alzheimer's Disease and the Aging Brain · 2018.12 – 2020.05 · New York, US*

- Integrated genomic, metabolomic, and clinical data to surface **13 key biomarkers (p<0.01)** from ~3,000 metabolites, resolving a confounder missed for eight months.
- Worked a high-dimensional, small-sample regime (146 samples × 3,000 variables); compared 10+ ML algorithms and chose **sPLS (84% accuracy with interpretability)**; built 20-year onset-risk models with Cox hazard and family-based GEE — research-competition top 3, Chair's Award, full-time neurosurgery offer.

## Education

- **M.S. Biostatistics**, Columbia University (2017–2019) — Chair's Award (annual graduation research competition)
- **B.A. Mathematics**, Baruch College, CUNY (2015–2017)
- **B.S. Biochemistry**, Kangwon National University (2006–2012) — Valedictorian, Dean's Award

## Skills

- **LLM Agent / GenAI** — RAG, Agentic RAG, Graph RAG, Self-RAG/CRAG, LangChain, LangGraph, Azure OpenAI, Azure AI Search, OpenAI/Claude API, Prompt Engineering
- **NLP / Deep Learning** — KLUE-RoBERTa, KoBERT, ALBERT, KoSRoBERTa, BiLSTM, LSTM, Hugging Face Transformers, PyTorch, KiwiPiePy/KoNLPy
- **ML / Statistics** — scikit-learn, HDBSCAN, regression/survival analysis, time series, causal inference (A/B test), experiment design, 95% CI, McNemar/Holm
- **Data / Backend Engineering** — Python, R, SQL (MySQL/PostgreSQL), SAS, FastAPI, Streamlit, Apache Airflow, Parquet, AST
- **Visualization / Docs** — Plotly, Matplotlib, Seaborn, R Shiny, ggplot2, Quarto, Jupyter, R Markdown
- **Cloud / DevOps** — Azure, Azure DevOps, Docker, Git/GitHub, Conda

## Patents (filed)

- **(First inventor)** Customized treatment method based on repeatedly-measured Ct values, Seegene (2022)
- **(First inventor)** Subscription system for a medical platform, Seegene (2022)
- **(First inventor)** Noise-test automation system for diagnostic equipment, Seegene (2021)
- **(First inventor)** Noise-level measurement algorithm for medical equipment, Seegene (2021)
- **(Co-inventor)** Prediction model for molecular diagnostics, Seegene (2022)
- **(Co-inventor)** Negative certificate for molecular diagnostics, Seegene (2022)
- **(Co-inventor)** Molecular-diagnostics system for community groups, Seegene (2022)

## Awards & Certifications

- **President's Award (R&D)** — noise-test automation system, Seegene (2021)
- **Chair's Award** — Graduation Practicum Research Competition, Columbia Biostatistics (2019)
- **Job Offer** — Taub Institute, Columbia University Irving Medical Center (2019)
- **Dean's Award** — valedictorian, Kangwon National University (2012)
- **Microsoft Azure certification training** — DP-203 (Data Engineering), DP-100 (Data Science), DP-300 (Database) (2025)
- **SAS Certified Base Programmer** (2018), **SIT TESOL Instruction Certification** (2014)
- **Completion** — EN62304 Medical Device SW Life Cycle (SGS, 2021), HIPAA (CUIMC, 2020)
- **Stipends** — $1,000 Mathematical Kinetic Modeling, CUNY (2015); $5,000 Medical Convergence Capstone Design, KNU (2012); full academic-excellence scholarship, KNU (2010–2011)

## Teaching & Mentoring

- **Mentor**, Seegene — AI Engineering (2024–2025), Data Standardization (2025), Statistical Analysis (2023–2024), Intro to Statistical Learning (2022)
- **Teaching Assistant**, Columbia University — Probability Theory (graduate, 2019)
- **Teaching Assistant**, CUNY — Calculus 1–3, Precalculus, Statistics (undergraduate, 2015–2016)
- **Private Tutor** — Calculus 1–2 (New York, 2021), GRE Math, TOEFL iBT (New York, 2014–2020)
- **Trainee Instructor** — SIT TESOL teaching, Rennert (2014)

## Languages

- Korean (native) · English (fluent)
