---
layout: page
title: RT-PCR Algorithm Reverse Engineering & Statistical Redesign
description: Reverse-engineering an undocumented legacy RT-PCR algorithm and designing a joint-estimation hybrid statistical model to remove systematic bias.
img: assets/img/projects/card_05_rtpcr-reverse-eng_en.svg
importance: 5
category: work
related_publications: false
mermaid:
  enabled: true
  zoomable: false
---

{% include lang_toggle.liquid active='en' ko='/ko/projects/5_rtpcr_reverse/' %}

**Role:** Data Scientist — algorithm analysis & redesign (6-person Data Science team) &nbsp;·&nbsp; **Period:** 2021.10 – 2023.04 &nbsp;·&nbsp; **Stack:** Matlab, Python, mechanistic + statistical modeling, joint parameter estimation, residual analysis

Reverse-engineered an **undocumented legacy Matlab algorithm** (10+ correction stages, 50+ empirical parameters) and designed a statistically rigorous replacement.

- **Legacy pain** — the deterministic rule stack grew exponentially with each new noise pattern; stage-by-stage sequential correction accumulated **systematic bias** with non-linear interactions, making sensitivity analysis impossible.
- **Design constraint** — regulatory clearance demanded explainability, so I reframed the problem as a **mechanistic + statistical hybrid** rather than a deep-learning black box.

{% include figure.liquid loading="eager" path="assets/img/projects/poster_05_rtpcr-reverse-eng_en.png" class="img-fluid rounded z-depth-1" zoomable=true alt="RT-PCR Algorithm Reverse Engineering & Statistical Redesign — project poster" %}

### Highlights

- **80% of the legacy algorithm's logic and dependencies interpreted and documented** — decision-tree visualizations of the branching structure and a detailed technical spec for the Data Engineering team's C++ port.
- **Joint-estimation hybrid model** — a composite of three preprocessing functions with an RT-PCR-kinetics logistic sigmoid, fit by estimating all parameters simultaneously. Sequential (backfitting) estimation accumulates per-stage bias; joint estimation removes it structurally.
- **Explicit statistical modeling of the residuals** — Gaussian-error assumption with white-noise checks, closed-form analytic gradients for stability and speed, and constrained optimization over physically valid parameter ranges.
- **Unified quantification and calling** — Ct values and positive/negative calls come from the same statistical model, folding curve-fitting, quantification, and calling into a single estimation problem.
- **(Organizational constraint)** the redesign was not adopted at the team-lead level — a lesson in balancing technical excellence against organizational buy-in. The statistical signal-processing and curve-fitting experience carried forward into the later [PCR baseline correction](/projects/3_pcr_baseline/) work.

### Approach

Phase 1 recovers the legacy logic; Phase 2 reformulates it as a single statistical model whose parameters map to interpretable curve features (slope, inflection, plateau) for regulatory justification.

```mermaid
flowchart TB
    L[Undocumented legacy Matlab<br/>10+ stages, 50+ params] --> RE[Reverse engineering<br/>80% interpreted + documented]
    RE --> SPEC[Decision-tree spec<br/>for C++ port]
    RE --> HY[Mechanistic + statistical<br/>hybrid composite function]
    HY --> JE[Joint parameter estimation<br/>vs. sequential backfitting]
    JE --> OUT[Systematic bias removed<br/>+ interpretable parameters]
```
