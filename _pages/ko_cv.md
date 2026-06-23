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

7년 이상 경력의 AI Engineer / Data Scientist. RAG, LLM 에이전트, NLP 기반 엔터프라이즈 AI 플랫폼을 아키텍처부터 설계·구축하고, 통계적으로 엄밀한 평가로 뒷받침한다. 전문 분야는 LLM 에이전트, RAG/Graph RAG, 딥러닝/NLP, 머신러닝, 실험설계, 통계분석이다.

## 경력

### Seegene — Data Scientist / AI Engineer

*2020.12 – 현재 · 대한민국*

전사 멀티 에이전트 플랫폼의 기술 리드/아키텍트로, 엔터프라이즈 AI 에이전트·RAG 플랫폼과 그 평가 체계를 설계·구축한다. 이전에는 진단 분야의 ML·통계 모델링을 담당했다.

- 도메인 특화 **멀티 에이전트 RAG 지식 플랫폼**을 아키텍처부터 총괄 설계·구축하고, 단일 에이전트 파일럿에서 전사 과제로 확장(전사 확장 중).
- **지식 QnA 챗봇** 설계 — 9개 sub-agent **Self-RAG/CRAG** 루프 + 토큰 스트리밍 + 출처 인용. 151건 질의에서 10개 지표 전수 통과(사용자 만족도 ~98%, 평균 응답 4.66초, 인용률 96.9%, 시스템 성공률 100%), 4모델 LLM-as-judge 평가에서 사실·추론 5.0/5.0.
- **자체 에이전트 오케스트레이션**이 범용 CLI 대비 **건당 비용 최대 ~17배 절감**을 벤치마크로 입증(paired t-test/McNemar/bootstrap CI, 6지표 Composite).
- **NLP 기반 데이터 표준화 시스템** — 검증 시간 **8시간 → 0.73초(99% 단축)**, 메타데이터 일관성 8.4% → 98.7%. 8개 모델 벤치마크(14클래스, 95% CI, McNemar+Holm)에서 KLUE-RoBERTa 96.88% 선정, 671K BiLSTM이 110M 모델과 통계적 동급임을 입증.
- 하드코딩 PCR 신호 baseline 알고리즘을 **데이터 기반 모델**로 재설계, 위음성률 **0.47% → 0.04%(91.49% 개선)**.
- 진단 장비 QC를 **2단계 LSTM + 10개 지표**로 자동화(신호 61,248개), QC 시간 ~93% 단축(연간 운영비 약 13배 절감) — R&D President's Award.
- **모델 평가·MLOps 체계** 구축 — LLM-as-judge 자동 채점 + 아키텍처 A/B 벤치마크 + 메트릭 로깅. IT/BT 20여 명 멘토링.

### 컬럼비아 의대 (CUIMC) — Taub Institute · Statistical Research Assistant

*2018.12 – 2020.05 · 미국 뉴욕*

알츠하이머병 바이오마커 발견을 위한 대규모 다중 오믹스 분석.

- 유전체·대사체·임상데이터 통합으로 약 3,000개 대사물질 중 **핵심 바이오마커 13개(p<0.01)** 발견, 8개월간 미발견 교란자 규명.
- 고차원 소표본 처리(변수 약 3,000개, 표본보다 변수가 훨씬 많은 환경), 10+ ML 알고리즘 비교 후 sPLS 선정(분류 정확도 84% + 해석력), Cox/GEE로 20년 발병 위험 모델 구축.

## 학력

- **M.S. Biostatistics**, Columbia University (2017–2019) — Chair's Award
- **B.A. Mathematics**, Baruch College, CUNY (2015–2017)
- **B.S. Biochemistry**, 강원대학교 (2006–2012) — 수석 졸업, 학장상

## 기술

- **LLM 에이전트 / GenAI** — RAG, Agentic RAG, Graph RAG, Self-RAG/CRAG, LangChain, LangGraph, Azure OpenAI, Azure AI Search, OpenAI/Claude API, 프롬프트 엔지니어링
- **NLP / 딥러닝** — KLUE-RoBERTa, KoBERT, ALBERT, BiLSTM/LSTM, Hugging Face Transformers, PyTorch, KiwiPiePy/KoNLPy
- **머신러닝 / 통계** — scikit-learn, HDBSCAN, 회귀/생존분석, 시계열, 인과추론(A/B Test), 실험설계
- **데이터 / 백엔드 엔지니어링** — Python, R, SQL(PostgreSQL), SAS, FastAPI, Streamlit, Apache Airflow, Parquet, AST, Docker, Azure DevOps

## 수상 · 특허

- **특허 출원 7건**(제1발명가 4건) — Ct 기반 맞춤 치료법, 의료 플랫폼 구독 시스템, 진단 장비 Noise Test 자동화, 의료 장비 Noise Level 측정 알고리즘 (제1발명가); 분자진단 예측 모델 등 (제2발명가). Seegene, 2021–2022.
- **President's Award** (R&D 부문 우수상), Seegene, 2021
- **Chair's Award** — Graduation Practicum Research Competition, Columbia Biostatistics, 2019

## 자격

- Microsoft Azure — DP-203(Data Engineering), DP-100(Data Science), DP-300(Database), 2025
- SAS Certified Base Programmer, 2018

## 언어

- 한국어 (모국어) · 영어 (유창)
