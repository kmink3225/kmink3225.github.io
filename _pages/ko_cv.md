---
layout: page
title: 이력서
permalink: /ko/cv/
nav: false
description: 김광민 — AI Engineer / Data Scientist 이력
toc:
  sidebar: left
---

<div style="text-align: right; margin-bottom: 1rem;"><a href="/cv/">English</a> · <strong>한국어</strong></div>

**김광민 (Kwangmin Kim)** · AI Engineer / Data Scientist · 대한민국 서울
[kmink3225@gmail.com](mailto:kmink3225@gmail.com) · [GitHub](https://github.com/kmink3225) · [LinkedIn](https://www.linkedin.com/in/kwangmin-kim-a5241b200/)

## 요약

7년 이상 경력의 AI Engineer / Data Scientist. RAG, LLM Agent, NLP 기반 엔터프라이즈 AI 플랫폼을 아키텍처부터 설계·구축한다. 사내 문서·지식·규정 기반 지식 QnA 챗봇을 포함한 엔터프라이즈 **AI Agent 지식 플랫폼**을 아키텍처부터 구축(사용자 만족도 **~98%**)했고, **데이터 표준화 시스템**을 성공시켜(검증 시간 **99% 단축**) 전사 멀티 Agent 플랫폼으로 확장, 총괄 설계 중이다. 자체 Agent orchestration으로 범용 대비 비용 **최대 ~18배 절감**을 벤치마크로 입증했으며, 진단 장비 QC 자동화로 연간 운영비 **약 13배 절감**, 통계적으로 엄밀한 모델 평가·실험설계를 병행한다. 다학제 팀(최대 20여 명)을 리딩했고 특허 **7건(제1발명가 4건)**을 출원했다.

**전문분야:** LLM Agent, RAG 시스템 설계·구현, NLP/딥러닝, 머신러닝, 실험설계, 통계분석, 진단 알고리즘.

## 경력

### Seegene — Data Scientist / AI Engineer

*SW연구소(Diagnosis IT General Research Institute) · 데이터 사이언스 / Core 개발팀 · 2020.12 – 현재 · 대한민국*

**엔터프라이즈 AI Agent 지식 플랫폼 구축** — Technical Lead / AI Architect, 2025.11 – 현재

- **전사 데이터 자산화**를 위한 도메인 특화 **멀티 Agent RAG 플랫폼**을 아키텍처부터 총괄 설계·구축(현업 실무진 배포, 전사 확장 중) — 지식 파편화·암묵지 소멸 문제 해결, 3대 Agent(지식 QnA, 데이터 표준화, 서열 추천 코드 분석)와 공유 Azure 인프라; 단일 Agent 계획을 멀티 Agent 대형 과제로 확장·승격, 2종 Agent를 목표 대비 **2개월 조기 완료**.
- **지식 QnA 챗봇** — 9개 sub-agent **Self-RAG/CRAG** 루프 + 토큰 스트리밍 + 출처 인용(Parent-Child + Hybrid Search(BM25+Vector) RAG 파이프라인); 10개 지표 전수 통과(평균 응답 **4.66초**, 인용률 96.9%, 시스템 성공률 100%, 검색 성공률 95.6%), 4모델 LLM-as-judge 평가에서 gpt-4.1 사실·추론 **5.0/5.0**, 사용자 만족도 **~98%**.
- **데이터 표준화 도우미 Agent** — Rule + ALBERT 분류기 + RAG **하이브리드 엔진**(LangGraph Reflexion 루프)으로 메타데이터 3종 자동 추천; 10개 지표 전수 통과, 만족도 **90.4%**, 평균 응답 3.75초, Fallback 0%.
- **서열 추천 코드 분석 Agent** — 약 40만 줄 Python(32개 레포, 1,453 파일)을 **40K AST 사실**, 코드 그래프(**11,729 노드 / 38,783 엣지**), 42K 검색 인덱스로 그라운딩; raw 범용 CLI vs 메타데이터+스킬 하네스 vs 자체 orchestration 3-아키텍처(7개 변형)를 6-지표 Composite + 통계검정으로 비교 — 하네스가 범용 CLI 대비 응답 유용성 향상(실무자 블라인드 평가로 교차검증), **자체 orchestration이 최우수**(GPT-5.4-mini Composite **0.977** 종합 1위, 11.6초, $0.076/건), 최고 비용 변형 대비 **~17배 저렴**, production 마무리 단계.
- **모델 평가·MLOps 체계** 구축 — LLM-as-judge 자동 채점(사실/추론/범위외/멀티턴) + 아키텍처 A/B 벤치마크(paired t-test, McNemar, Cohen's d, bootstrap CI) + 메트릭 로깅; 클라우드 운영비 추정 대비 **32% 절감**, 자체 하네스 전략으로 벤더 Lock-in 대비.
- **Microsoft 워크숍 2회** 기술 주도 — Azure 기반 Copilot CLI 대비 자체 오케스트레이션 토론에서 **MS architect와 엔지니어 7명을 자체 아키텍처로 설득**.

**자연어처리 기반 데이터 표준화 시스템 구축** — Technical Lead (IT/BT 20여 명 멘토링), 2024.10 – 2025.09

- 현업의 메타데이터 불일치 이슈를 **문제 정의** → NLP + Rule + RAG 기반 표준화 시스템 구축 총괄; 파일럿 성공 후 **전사 적용** 전환, **후속 AI Agent 플랫폼으로 확장된** 대형 과제의 출발점.
- 자동화 성과(사용자 설문·운영 측정): 검증 시간 **8시간 → 0.73초(99%↓)**, 부서 간 문의 **월 70 → 4건(94.3%↓)**, 메타데이터 일관성 **8.4% → 98.7%**, 완전성 **29.6% → 100%**.
- 도메인 분류기 **8-모델 벤치마크**(KLUE-RoBERTa, XLM, KoBERT, ALBERT, mBERT, BiLSTM, DistilKoBERT, e5; 동일 조건 14클래스, 7,698건, stratified, 95% CI, McNemar(Yates)+Holm 28쌍) → **KLUE-RoBERTa 96.88%** 최고(상위 5개 트랜스포머 통계적 동률).
- **강건성·교차검증 5종** — 5-fold CV로 **671K BiLSTM이 110M KLUE와 통계적 동급**(96.18%±0.41% vs 96.35%, p=0.73) + **1.48ms 최속 추론**(12.49ms 대비) 발굴; suffix ablation(−51%p), RAG holdout(합성 과적합 가설 기각), 노이즈플로어로 정확도 상한이 데이터 한계임을 진단.
- **학습데이터 엔지니어링** — LLM·규칙·RAG 3소스 9,168건 → 라벨 정규화, 충돌 29건 식별, 중복 제거(1,466건) → 7,698건 큐레이션; 표준단어 582, 도메인 매핑 147 사전 구축.
- **규칙 기반 명명 표준화 엔진**(규칙 14개 + 물리명·약어 자동 생성); 유사어 클러스터링(ko-sroberta-multitask + HDBSCAN, 2,048 → 569 클러스터); **pytest 60, GitHub Actions CI, Docker**로 재현 가능 ML 엔지니어링 확립.

**시계열 PCR 신호 baseline 보정 알고리즘 최적화** — 프로젝트 PM (DS 3, DE 1), 2024.01 – 2024.09

- 하드코딩 레거시 baseline 알고리즘을 혼합 기저함수 기반 **데이터 기반 모델**로 재설계, 위음성률 **0.47% → 0.04%(91.49%↓)**; Matlab → Python low-level 리팩터링 + 경량 선형회귀 실시간 최적화, 5종 경쟁 알고리즘 대비 잔여신호 백색잡음 근사도 1위.

**FDA 인허가용 진단 알고리즘 안전성 통계 분석** — 프로젝트 PM (다학제 16명), 2023.05 – 2023.12

- FDA Software Validation 대응 **통계 분석 파이프라인** 설계·자동화, 검증 기간 **6개월 → 3주(87.5%↓)**, 통계 신뢰도 99.2%; C++ 포팅용 통계 검정 구현(2-Way RM-ANOVA, McNemar, Breslow-Day, Cochran-Mantel-Haenszel), 사내 고유 **Switch Model** ablation, Airflow → R + Quarto로 200페이지 V&V 보고서 반자동 생성.

**RT-PCR 진단 알고리즘 Reverse Engineering 및 통계 모델링 개선안 설계** — Data Scientist (6인 팀), 2021.10 – 2023.04

- 주석 없는 레거시 Matlab 알고리즘(10+단계, 50+ 경험적 파라미터)을 reverse engineering으로 논리 흐름·의존성 **80% 해석**, C++ 포팅용 기술 명세서 완성; RT-PCR kinetics 기반 로지스틱 시그모이드 합성함수와 정규분포 결합추정(joint estimation)으로 systematic bias 해소 프레임워크 확립.

**PCR 장비 QC Test 프로토콜 설계 및 장비 성능 분류 (A+/A/B/F)** — 프로젝트 PM (다학제 11명), 2020.12 – 2021.09

- 수동 엑셀 QC를 **LSTM 2단계 예측 + 10개 성능 지표 등급 분류**로 자동화, QC 시간 약 **400h → 28h/100대(93%↓)**, 연간 운영비 **약 13배 절감(~8억원)**; 2,201대 장비·**61,248개 신호**로 합/불 94.5%, 등급 82.7% 분류, PCA·t-SNE·DBSCAN 이상탐지 + R Shiny 대시보드 — **R&D 부문 우수상(President's Award)**, **제1발명가 특허 2건**.

### Columbia University Irving Medical Center (CUIMC) — Taub Institute · Statistical Research Assistant

*알츠하이머병·뇌 노화 연구소 · 2018.12 – 2020.05 · 미국 뉴욕*

- 유전체·대사체·임상데이터 통합 분석으로 약 3,000개 대사물질 중 **핵심 바이오마커 13개(p<0.01)** 발견, 8개월간 미발견 교란자 규명.
- 고차원 소표본(146샘플 × 3,000변수) 처리, 10+ ML 알고리즘 비교 후 **sPLS 선정(분류 정확도 84% + 해석력)**, Cox Hazard·GEE(Family-based)로 20년 잠복기 발병 위험 모델 구축 — 연구 경진대회 top 3, 학과장상, 신경외과 정규직 제안.

## 학력

- **M.S. Biostatistics**, Columbia University (2017–2019) — 연례 졸업 연구 대회 학과장상(Chair's Award)
- **B.A. Mathematics**, Baruch College, CUNY (2015–2017)
- **B.S. Biochemistry**, 강원대학교 (2006–2012) — 수석 졸업, 학장상

## 기술

- **LLM Agent / GenAI** — RAG, Agentic RAG, Graph RAG, Self-RAG/CRAG, LangChain, LangGraph, Azure OpenAI, Azure AI Search, OpenAI/Claude API, Prompt Engineering
- **NLP / 딥러닝** — KLUE-RoBERTa, KoBERT, ALBERT, KoSRoBERTa, BiLSTM, LSTM, Hugging Face Transformers, PyTorch, KiwiPiePy/KoNLPy
- **머신러닝 / 통계** — scikit-learn, HDBSCAN, 회귀/생존분석, 시계열, 인과추론(A/B Test), 실험설계, 95% CI, McNemar/Holm
- **데이터 / 백엔드 엔지니어링** — Python, R, SQL(MySQL/PostgreSQL), SAS, FastAPI, Streamlit, Apache Airflow, Parquet, AST
- **시각화 / 문서화** — Plotly, Matplotlib, Seaborn, R Shiny, ggplot2, Quarto, Jupyter, R Markdown
- **Cloud / DevOps** — Azure, Azure DevOps, Docker, Git/GitHub, Conda

## 특허 (출원)

- **(제1발명가)** 반복 측정된 Ct 값에 기초한 맞춤화 치료 방법, Seegene (2022)
- **(제1발명가)** 의료 플랫폼을 위한 구독 시스템, Seegene (2022)
- **(제1발명가)** 진단 장비의 Noise Test 자동화 시스템, Seegene (2021)
- **(제1발명가)** 의료 장비의 Noise Level 측정 알고리즘, Seegene (2021)
- **(제2발명가)** 분자 진단을 위한 예측 모델, Seegene (2022)
- **(제2발명가)** 분자 진단 음성 증명서, Seegene (2022)
- **(제2발명가)** Community Group을 위한 분자 진단 시스템, Seegene (2022)

## 수상 · 자격

- **President's Award** — R&D 부문 우수상(Noise Test 자동화 시스템), Seegene (2021)
- **Chair's Award** — Graduation Practicum Research Competition, Columbia Biostatistics (2019)
- **Job Offer** — Taub Institute, Columbia University Irving Medical Center (2019)
- **학장상** — 성적 우수 수석 졸업, 강원대학교 (2012)
- **Microsoft Azure 자격 교육 이수** — DP-203(Data Engineering), DP-100(Data Science), DP-300(Database) (2025)
- **SAS Certified Base Programmer** (2018), **SIT TESOL Instruction Certification** (2014)
- **수료** — EN62304 Medical Device SW Life Cycle (SGS, 2021), HIPAA (CUIMC, 2020)
- **장학·Stipend** — $1,000 Mathematical Kinetic Modeling, CUNY (2015); $5,000 Medical Convergence Capstone Design, KNU (2012); 성적 우수 전액 장학금, 강원대학교 (2010–2011)

## 강의 · 멘토링

- **Mentor**, Seegene — AI Engineering (2024–2025), Data Standardization (2025), Statistical Analysis (2023–2024), An Introduction to Statistical Learning (2022)
- **Teaching Assistant**, Columbia University — Probability Theory (석사 수준, 2019)
- **Teaching Assistant**, CUNY — Calculus 1–3, Precalculus, Statistics (학부, 2015–2016)
- **Private Tutor** — Calculus 1–2 (New York, 2021), GRE Math, TOEFL iBT (New York, 2014–2020)
- **Trainee Instructor** — SIT TESOL teaching, Rennert (2014)

## 언어

- 한국어 (모국어) · 영어 (유창)
