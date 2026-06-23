---
layout: page
title: Alzheimer's Multi-Omics Biomarker Discovery
description: Integrating genomic, metabolomic, and clinical data at Columbia / Taub Institute to surface candidate Alzheimer's biomarkers.
img: assets/img/4.jpg
importance: 4
category: work
related_publications: false
mermaid:
  enabled: true
  zoomable: false
---

**Role:** Statistical Research Assistant, Columbia University Irving Medical Center — Taub Institute &nbsp;·&nbsp; **Stack:** R, Cox / GEE, sPLS, Lasso/Ridge/RF/SVM/GBM, PCA/K-means/DBSCAN

A graduate-level biostatistics project on **large-scale multi-omics analysis** for Alzheimer's disease biomarker discovery.

### Highlights

- Integrated **genomic, metabolomic, and clinical** data to surface **13 key biomarkers (p < 0.01)** from ~3,000 metabolites, and uncovered a confounder that had gone undetected for eight months.
- Handled a high-dimensional, small-sample setting (**~3,000 variables, far more features than samples**) with MCAR/MAR/MNAR-aware missing-data treatment and a 3-stage EDA → statistics → ML validation.
- Compared 10+ ML algorithms and selected **sPLS** (84% classification accuracy with interpretability); built 20-year onset-risk models with Cox hazard and family-based GEE, and characterized GWAS + metabolite associations.
- Research competition top-3; Chair's Award; full-time offer from the Taub Institute.

### Approach

A staged pipeline integrates three data modalities, treats missingness explicitly, and validates findings from exploratory analysis through statistics to machine learning.

```mermaid
flowchart TB
    G[Genomic] --> INT[Multi-omics integration]
    M[Metabolomic] --> INT
    C[Clinical] --> INT
    INT --> MISS[Missing-data treatment<br/>MCAR / MAR / MNAR]
    MISS --> VAL[EDA, statistics, ML validation]
    VAL --> SEL[10+ models compared<br/>sPLS selected, 84% accuracy]
    SEL --> OUT[13 biomarkers<br/>+ 20-year risk models]
```
