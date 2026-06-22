---
layout: page
title: 프로젝트
permalink: /ko/projects/
nav: false
description: AI/LLM 엔지니어링과 데이터 사이언스 주요 작업. 운영 세부사항은 회사 IP 보호를 위해 추상화했다.
toc:
  sidebar: left
---

<div style="text-align: right; margin-bottom: 1rem;"><a href="/projects/">English</a> · <strong>한국어</strong></div>

> 아키텍처와 방법론은 상위 수준으로만 기술한다. 운영 코드와 내부 데이터는 비공개다.

## 엔터프라이즈 멀티 에이전트 RAG 플랫폼

*역할: 기술 리드 / 아키텍트 · 스택: Python, LangChain, LangGraph, Azure OpenAI, Azure AI Search, FastAPI*

도메인 특화 **멀티 에이전트 RAG 지식 플랫폼**을 아키텍처부터 총괄 설계·구축하고, 단일 에이전트 파일럿에서 전사 과제로 확장했다(초기 ~30명 배포, 전사 확장 중).

- **지식 QnA 챗봇** — 9개 sub-agent Self-RAG/CRAG 루프 + 토큰 스트리밍 + 출처 인용. 151건 질의 10개 지표 전수 통과(만족도 ~98%, 4.66초, 인용률 96.9%, 성공률 100%), 4모델 LLM-as-judge에서 사실·추론 5.0/5.0.
- **자체 오케스트레이션 vs 범용 CLI** — 최상위 구성에서 건당 비용 **최대 ~17배 절감**(paired t-test/McNemar/Cohen's d/bootstrap CI, 6지표 Composite).
- **RAG 파이프라인** — Parent-Child + Contextual Chunking, 하이브리드 검색(BM25+Vector), Child→Parent 매핑, 리랭킹으로 환각 억제. LangChain → LangGraph → Agentic 3단계 로드맵.

## NLP 기반 데이터 표준화 시스템

*역할: 기술 리드(IT/BT 20여 명 멘토링) · 스택: PyTorch, Transformers, KLUE-RoBERTa, BiLSTM, HDBSCAN, RAG, pytest, Docker*

현업 메타데이터 불일치 문제를 정의하고 Rule + 분류기 + RAG 하이브리드 시스템으로 해결, 파일럿 성공 후 전사 적용·후속 AI 플랫폼의 출발점이 되었다.

- 검증 시간 **8시간 → 0.73초(99% 단축)**, 부서 간 문의 월 70 → 4건(94.3%↓), 일관성 8.4% → 98.7%, 완전성 29.6% → 100%.
- **8개 모델 벤치마크**(14클래스, 7,698건, stratified, 95% CI, McNemar+Holm) — KLUE-RoBERTa 96.88% 최고, 5-fold CV로 671K BiLSTM이 110M 모델과 통계적 동급(p=0.73) 입증, 1.48ms 경량 배포안 도출.

## 진단 신호 모델링 & QC 자동화

*역할: 프로젝트 PM / Data Scientist · 스택: Python, R, LSTM, 기저함수 모델링, PCA/t-SNE/DBSCAN, R Shiny*

- **PCR 신호 baseline 보정** — 하드코딩 레거시를 데이터 기반 혼합 기저함수 모델로 재설계, 위음성률 **0.47% → 0.04%(91.49% 개선)**, 5종 경쟁 알고리즘 대비 백색잡음 근사도 1위.
- **장비 QC 자동화** — 2단계 LSTM + 10개 지표(장비 2,201대·신호 61,248개), QC 시간 ~93% 단축(연간 운영비 약 13배 절감), 합/불 분류 94.5%. R&D President's Award 및 제1발명가 특허 2건.

## 알츠하이머 멀티 오믹스 바이오마커 발견

*역할: Statistical Research Assistant, 컬럼비아 의대 Taub Institute · 스택: R, Cox/GEE, sPLS, Lasso/Ridge/RF/SVM/GBM*

- 유전체·대사체·임상데이터 통합으로 약 3,000개 대사물질 중 **핵심 바이오마커 13개(p<0.01)** 발견, 8개월간 미발견 교란자 규명.
- 고차원 소표본(146 샘플 × 3,000 변수), 10+ ML 비교 후 sPLS 선정(정확도 84% + 해석력), Cox/GEE로 20년 발병 위험 모델 구축. 연구 경진대회 top-3, Chair's Award, Taub Institute 정규직 제안.
