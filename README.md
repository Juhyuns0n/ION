# ION

ION은 **예비 부모와 0~7세 자녀 부모를 위한 LLM·STT 기반 맞춤형 교육 및 연령별 부모교육 앱**으로,  
부모–아이 별 상황을 분석하여 **사용자 맞춤형 Workbook, 대화 분석 Voice Report, 양육 상담 Chatbot** 기능을 제공하는 서비스입니다.

본 레포지토리는 ION 캡스톤 프로젝트의 **Android 앱, Backend 서버, AI 모듈**을 포함합니다.

---


## 🔍 Project Overview

ION은 다음과 같은 문제의식에서 출발했습니다.

- 체계적인 부모 교육에 대한 **접근성 부족**
- 이론 위주의 교육으로 인한 **실제 상황 적용의 어려움**
- 부모·아이 상황에 맞춘 **개인화된 구체적 조언의 부재**

이를 해결하기 위해 ION은
- **학습 - 실천 - 상담**의 흐름을 하나의 모바일 서비스로 통합한
AI 기반 육아 지원 시스템을 구현했습니다.

ION은 다음 세가지 핵심 기능으로 구성됩니다.

## 📘 Workbook (학습 단계)
**연령·발달·성향에 맞춘 부모 교육 커리큘럼 제공**
* 출산 전부터 0–5세까지의 부모를 대상으로 한 단계별 부모교육 워크북
* 회원가입 시 입력한 자녀 연령, 성향, 부모 정보 등을 반영해 **개인화된 워크북 콘텐츠 자동 생성**
* 아동발달 이론 기반의:
* + 이론 설명 콘텐츠
  + 선택형/서술형 액티비티
  + 가상 아이와의 대화 시뮬레이션(상황제시형)
* 단순 정보 전달이 아닌, **“생각해보고 연습해보는 학습 경험”**에 초점 
→ 체계적인 부모 교육을 시간·장소 제약 없이 제공

## 🎙 Voice Report (실천 단계)
**부모–아이 실제 대화를 기반으로 한 행동 피드백 제공**
* 홈캠·녹음 등을 통해 수집한 **부모–아이 실대화 음성 데이터 분석**
* STT + 화자 분리(Diarization)를 통해 대화 구조를 분석하고,
* AI가 다음과 같은 항목에 대해 **행동 피드백 리포트 생성**
* + 언어적 반응 패턴
  + 감정 표현 방식
  + 부적절한 표현에 대한 대체 표현 제안
  + 긍정적 양육 행동 포인트
  + 부모-아이 발화 비율
→ 이론에서 배운 내용을 **실제 양육 상황에서 어떻게 적용하고 있는지 명확하게 확인 가능**

## 💬 Parenting Chatbot (상담 단계)
**24시간 즉각적인 개인 맞춤형 육아 상담 지원**
* 사용자의 질문에 대해:
* + 회원가입 시 입력한 사용자·자녀 특성
  + 신뢰 가능한 육아 전문 자료
  를 종합하여 **상황 맥락을 고려한 답변 제공**
* 단순 일반 답변이 아닌, **부모 상황에 맞춘 비교적 구체적인 조언** 제공
* 육아 전문가 상담이나 오프라인 교육의:
* + 긴 대기 시간
  + 높은 비용
  + 접근성 한계를 보완
→ **언제든지 접근 가능한 육아 상담 창구 역할**

---

## 🧩 System Components

### 📱 Android Application (Front-end)

ION Android 앱은 사용자 인증, 부모교육 워크북 콘텐츠 제공, 피드백 분석 결과 조회, 챗봇 상담 제공을 담당합니다.

### APK 다운로드
- 👉 **GitHub Release (v1.0)**  
  https://github.com/Juhyuns0n/ION/releases/tag/v1.0

### 설치 방법
1. APK 파일 다운로드
2. Android 설정 → *알 수 없는 앱 설치 허용*
3. APK 실행 및 설치  
   *(Play Protect 경고가 표시될 수 있음)*

### 앱 정보
- **Build type**: Debug  
- **Minimum Android**: Android 9 (API 28)  
- **Target / Compile SDK**: API 35 (Android 15)  
- **Network**: 인터넷 연결 필요
- **Base URL**: http://3.38.149.207:8080/

> ⚠️ **현재 서버는 수업 시연 완료 후 종료(offline) 상태입니다.**  
> 앱 실행은 가능하나, 서버 통신이 필요한 기능은 동작하지 않을 수 있습니다.

📌 Android 프로젝트 상세 설명은 `android/README.md`를 참고하세요.

---

## 🧩 System Components

### 📱 Android Application
- 사용자 인증
- 부모 교육 워크북 제공
- Voice Report 및 분석 결과 시각화
- 챗봇 상담 UI 제공

### 🖥 Back-end Server
- 사용자 및 도메인 데이터 관리
- Voice Report / Workbook / Chatbot API 제공
- MySQL(RDS) 기반 데이터 영속화
- AI 마이크로서비스 연동

### 🤖 AI Module
- 음성·텍스트 기반 상호작용 분석
- 피드백 및 교육 콘텐츠 생성
- 백엔드 서버와 REST API 기반 연동

---

## 📂 Repository Structure

```text
ION/
├── android/        # Android Application (APK 포함)
├── backend/        # Spring Boot Back-end Server
├── ai/             # AI 분석 모듈 (Python)
├── docs/           # 프로젝트 보고서
├── README.md       # Root README
└── .gitignore

---

## **📦 Android APK**

* **APK 다운로드 (GitHub Release)**
 👉 https://github.com/Juhyuns0n/ION/releases/tag/v1.0
  Android APK는 **설치 및 UI 확인 목적**으로 제공됩니다.
- APK는 설치 및 UI 흐름 확인용으로 제공됩니다.

---

## **📌 Notes**

- 본 프로젝트는 **캡스톤 디자인 수업 제출용**으로 개발되었습니다.
- 서버는 **수업 시연 완료 후 종료(offline)** 된 상태입니다.
- 테스트 계정 및 전체 시연은 **수업 시간 중 완료**되었습니다.

