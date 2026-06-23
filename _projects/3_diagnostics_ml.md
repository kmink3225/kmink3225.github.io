---
layout: page
title: Diagnostic Signal Modeling & QC Automation
description: Data-driven redesign of a PCR signal-correction algorithm, and LSTM-based automation of equipment quality control.
img: assets/img/3.jpg
importance: 3
category: work
related_publications: false
mermaid:
  enabled: true
  zoomable: false
---

<div style="text-align: right; margin-bottom: 1rem;"><strong>English</strong> · <a href="/ko/projects/3_diagnostics_ml/">한국어</a></div>

**Role:** Project PM / Data Scientist &nbsp;·&nbsp; **Stack:** Python, R, LSTM, linear/basis-function modeling, PCA/t-SNE/DBSCAN, R Shiny

Two diagnostics projects where statistical rigor drove measurable safety and cost outcomes.

### PCR signal baseline correction

- Redesigned a hard-coded legacy baseline algorithm into a **data-driven mixed-basis-function model**, cutting the false-negative rate **0.47% → 0.04% (91.49% improvement)**.
- Ranked #1 in residual-signal white-noise approximation against 5 competing algorithms; refactored Matlab → Python with real-time linear-regression optimization.

### Equipment QC automation

- Replaced manual Excel QC with a **two-stage LSTM + 10 graded performance metrics**, cutting QC time ~93% (≈13× annual operating-cost reduction).
- Trained on 2,201 devices / 2,552 runs / **61,248 signals**: pass-fail classification 94.5%, grade classification 82.7%; anomaly detection via PCA, t-SNE, DBSCAN, 3-sigma with an R Shiny real-time dashboard.
- Recognized with an **R&D President's Award** and two first-inventor patents.

### Approach

Both projects replaced a manual or hard-coded baseline with a measured, data-driven model.

```mermaid
flowchart TB
    subgraph PCR[PCR baseline correction]
      direction TB
      L[Hard-coded legacy algorithm] --> D[Data-driven<br/>mixed-basis-function model]
      D --> FN[False-negative<br/>0.47% to 0.04%]
    end
    subgraph QC[Equipment QC automation]
      direction TB
      M[Manual Excel QC] --> LSTM[Two-stage LSTM<br/>+ 10 graded metrics]
      LSTM --> T[QC time ~93% lower]
    end
```
