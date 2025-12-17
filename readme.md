# 🤖 ION AI Module

ION의 AI 모듈은 **부모–자녀 상호작용 데이터를 기반으로 개인화된 육아 교육과 피드백을 제공**하는 핵심 분석 시스템입니다.  
LLM·STT 기술을 활용하여 **워크북 생성, 음성 대화 분석, 육아 상담 챗봇** 기능을 담당합니다.

> 본 디렉토리는 **Python 기반 AI 마이크로서비스** 구현을 포함하며,  
> Spring Boot 백엔드와 **REST API (WebClient)** 를 통해 연동됩니다.

---

## 🎯 AI Module Responsibilities

- **LLM 기반 맞춤형 육아 콘텐츠 생성**
- **부모–자녀 음성 대화 분석 및 피드백 리포트 생성**
- **전문 자료 기반 RAG(Chatbot) 상담 제공**
- **사용자 프로필(부모 성향, 자녀 연령 등) 반영 개인화**
- **백엔드 API 요청에 대한 AI 분석 응답 제공**

---

## 🧠 AI Features Overview

### 1️⃣ Personalized Parenting Workbook
- 부모 프로필(자녀 연령, 양육 성향, 목표 등)을 기반으로 **개인화된 워크북 콘텐츠 자동 생성**
- 검증된 육아 이론 커리큘럼과 LLM을 결합한 **단계별 학습 구조**
- 서술형 + 선택형 질문 구성 및 대화형 시뮬레이션 활동 설계

---

### 2️⃣ AI Voice Report (Parent–Child Interaction Analysis)
- 부모–자녀 간 음성 대화를 업로드하면:
  - **STT + 화자 분리**
  - **대화 흐름·표현·감정 분석**
  - **구체적인 개선 제안 및 강점 피드백 제공**
- 90초 이내 음성 파일 처리
- 구조화된 JSON 리포트 생성 (표현 분석, 감정 타임라인, 빈도 분석 등)

---

### 3️⃣ LLM-Based Parenting Chatbot (RAG)
- **RAG (Retrieval-Augmented Generation)** 구조 기반 육아 상담 챗봇
- 전문 육아 서적을 벡터화하여 **환각(hallucination) 최소화**
- 사용자 프로필 + 질문 컨텍스트를 결합한 **맞춤형 답변**
- 공감적 어조, 의학적 판단 회피, 단계별 실행 팁 제공

---

## 🧩 System Architecture (AI)

```text
Spring Boot Backend
        │
        │ REST API (WebClient)
        ▼
FastAPI-based AI Services
 ├── chatbot      # RAG 기반 육아 상담
 ├── voicereport  # 음성 분석 및 피드백
 └── workbook     # 맞춤형 워크북 생성
        │
        ▼
OpenAI API (LLM / STT)
AWS RDS (MySQL)
```

---

## 🛠 Tech Stack

### Core
- **Python 3**
- **FastAPI** (비동기 REST API)
- **OpenAI API**
  - GPT-5-mini (LLM)
  - GPT-4o-transcribe-diarize (STT + Speaker Diarization)

### NLP / ML
- **KR-SBERT** (한국어 특화 문장 임베딩)
- **Cosine Similarity** 기반 벡터 검색
- **RAG (Retrieval-Augmented Generation)** 구조 적용

### Database
- **AWS RDS (MySQL)**
  - 사용자 프로필 데이터
  - 육아 전문 텍스트
  - 임베딩 벡터
  - AI 분석 결과 저장

---

## 🔐 Personalization Strategy

AI는 다음 사용자 정보를 기반으로 **개인화된 분석 결과 및 콘텐츠**를 생성합니다.

- 자녀 연령 (발달 단계 반영)
- 부모 양육 성향 (PSDQ 검사 기반)
- 양육 목표
- 아이 성향
- 선호 말투 / 언어
- 건강 및 특이사항

---

## ⚠️ Notes

- 본 AI 모듈은 **캡스톤 디자인 수업 제출용**으로 개발되었습니다.
- 서버 및 AI API 연동은 **수업 시연 완료 후 종료(offline)** 된 상태입니다.
- AI 기능의 **End-to-End Flow 및 성능 검증은 시연 환경에서 완료**되었습니다.

---

## 📎 References

- 전문 육아 서적 및 아동발달 센터 검수 자료
- Robinson et al., 1995 — *PSDQ (Parenting Styles and Dimensions Questionnaire)*
- **Retrieval-Augmented Generation (RAG)** Architecture

---

## 🧩 Related Modules

- Android Client: `android/`
- Back-End Server: `backend/`

각 모듈의 상세 구조 및 구현 내용은
해당 디렉토리의 README를 참고하세요.
