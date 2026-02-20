# KT AIVLE School 8기 AI트랙 충남충북7반 14조

# 빅프로젝트 RAILDOCK - **AI 기반 철도 시설물 유지보수 의사결정 지원 플랫폼**

## 프로젝트 개요

RAILDOCK은 영상 데이터 기반 철도 시설물 결함을 탐지하고,
GIS 기반 모니터링과 LLM-RAG 기술을 결합하여
**유지보수 판단 및 사고 예방을 지원하는 통합 관제 플랫폼**입니다.
최근 철도 사고의 주요 원인이 인적 오류 및 시설물 노후화에 있다는 점에 주목하여,
AI 기반 자동 탐지와 규정 연계 의사결정 시스템을 통해
**선제적 유지보수 체계 구축**을 목표로 하였습니다.

## 참여인원
|                    [성기현(조장)](https://github.com/castlehyuuuun)                    |                    [박기현](https://github.com/stcheesecake)                  |                    [서범수](https://github.com/SeoBeomsu)                  |                   [윤후성](https://github.com/HuSngYn)                  |                    [유승환](https://github.com/yush0822)                  |                    [고제은](https://github.com/jeeun-ko)                  |                    [진승호](https://github.com/seung-h0)                  |
| :--------------------------------------------------------------------: | :-----------------------------------------------------------------------: | :---------------------------------------------------------------------: | :--------------------------------------------------------------: | :--------------------------------------------------------------: | :--------------------------------------------------------------: | :--------------------------------------------------------------: |
| <img width="100" height="150" alt="성기현" src="https://github.com/user-attachments/assets/dda002c8-1ec0-4212-8051-0d5d60e7ab03" /> | <img width="100" height="150" alt="박기현" src="https://github.com/user-attachments/assets/8404867d-425a-4cd5-97d9-6bbabf134050" /> | <img width="100" height="150" alt="서범수" src="https://github.com/user-attachments/assets/09feb43c-88d7-4fcf-9fb8-3f6e9cf5f321" /> | <img width="100" height="150" alt="윤후성" src="https://github.com/user-attachments/assets/d059428b-4f1b-4e7a-849d-23b11bacf974" /> | <img width="100" height="150" alt="유승환" src="https://github.com/user-attachments/assets/42936e63-9a9e-46c3-97d3-2bf2ec522ff9" /> | <img width="100" height="150" alt="고제은" src="https://github.com/user-attachments/assets/2f7e0b8f-a020-4e97-8432-8054a48bae37" /> | <img width="100" height="150" alt="진승호" src="https://github.com/user-attachments/assets/b7e94426-d5e6-48fc-b8a3-21449e449b35" /> |
| AI / EDA <br> VisionModel <br> LLM-RAG | AI / EDA <br> VisionModel <br> PPT| BE / FE <br> AWS / Deploy| BE / AI <br> AWS / Deploy| FE <br> UIUX Design| AI / EDA <br> RAG| AI / EDA <br> RAG / PPT |


## 문제 인식

* 증가하는 철도 사고 및 피해 규모
* 인력 중심 점검 체계의 한계
* 시설물 데이터 관리 및 실시간 모니터링 부족
* 규정 기반 조치가 체계적으로 연결되지 않는 구조

👉 철도 안전의 구조적 개선이 필요하다는 문제의식에서 출발하였습니다.

---

## 🏗 시스템 구성도

<img width="450" height="750" alt="시스템 구성도" src="https://github.com/user-attachments/assets/af3fb9a2-6ba5-494d-a1ec-2c8cd2e9eab0" />

### 🔹 아키텍처 개요

| Layer              | 주요 기술                                                            | 설계 및 구현 포인트                                                                                         |
| ------------------ | ---------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| **Frontend**       | React<br>TypeScript<br>OpenLayers<br>React Query                 | • GIS 기반 철도 노선 및 결함 위치 시각화<br>• 실시간 상태 반영 UI 구조<br>• 서버 상태 관리 최적화                                   |
| **Backend**        | Kotlin<br>Spring Boot<br>Spring Security                         | • 세션 기반 인증/인가 구조<br>• Scheduler + Worker 패턴 적용<br>• REST API 모듈 분리 설계                               |
| **AI Server**      | YOLO-LAF<br>LWM<br>C2f-SCConv<br>EMA                             | • 시설물 결함 탐지 모델 커스터마이징<br>• 연산량 감소 및 탐지 성능 개선<br>• HuggingFace 기반 모델 버전 관리<br>• 피드백 기반 파인튜닝 파이프라인 구축 |
| **LLM-RAG Server** | Gemini API<br>Vector DB<br>RAG                                   | • 규정 문서 벡터화 및 검색 구조 설계<br>• 규정 기반 유지보수 조치 권고 생성<br>• 보고서 형식 응답 구조화                                  |
| **Cloud**          | AWS EC2<br>AWS S3<br>CloudFront<br>ECR<br>CodeBuild / CodeDeploy | • 서버 역할 분리 아키텍처<br>• CDN 기반 파일 제공 구조<br>• CI/CD 자동 배포 파이프라인 구축                                      |


| 구분              | **Frontend**                                              | **Backend**                                                        | **AI Server**                                                                                 | **LLM-RAG Server**                                              | **Cloud**                                                        |
| --------------- | --------------------------------------------------------- | ------------------------------------------------------------------ | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------- | ---------------------------------------------------------------- |
| **주요 기술**       | React<br>TypeScript<br>OpenLayers<br>React Query          | Kotlin<br>Spring Boot<br>Spring Security                           | YOLO-LAF<br>LWM<br>C2f-SCConv<br>EMA                                                          | Gemini API<br>Vector DB<br>RAG                                  | AWS EC2<br>AWS S3<br>CloudFront<br>ECR<br>CodeBuild / CodeDeploy |
| **설계 및 구현 포인트** | • GIS 기반 철도 노선 시각화<br>• 실시간 결함 위치 확인 UI<br>• 서버 상태 관리 최적화 | • 세션 기반 인증/인가 구조<br>• Scheduler + Worker 패턴<br>• REST API 모듈 분리 설계 | • 시설물 결함 탐지 모델 커스터마이징<br>• 연산량 감소 및 탐지 성능 개선<br>• HuggingFace 기반 모델 관리<br>• 피드백 기반 파인튜닝 파이프라인 | • 규정 문서 벡터화 및 검색 구조 설계<br>• 유지보수 조치 권고 자동 생성<br>• 보고서 형식 응답 구조화 | • 서버 역할 분리 아키텍처<br>• CDN 기반 파일 제공 구조<br>• CI/CD 자동 배포 파이프라인      |


* **Frontend**

  * React + TypeScript
  * OpenLayers 기반 GIS 지도 시각화
  * 실시간 결함 위치 확인 UI
  * React Query 기반 서버 상태 관리

* **Backend**

  * Kotlin + Spring Boot
  * 세션 기반 인증/인가
  * Scheduler + Worker 패턴 기반 AI 처리 구조
  * REST API 기반 모듈 분리 설계

* **AI Server**

  * YOLO-LAF 기반 시설물 결함 탐지
  * LWM, C2f-SCConv, EMA 구조 개선 적용
  * HuggingFace 모델 관리
  * 피드백 기반 파인튜닝 파이프라인 구축

* **LLM-RAG 서버**

  * Gemini 기반 규정 연계 질의응답
  * 규정 문서 벡터화 및 RAG 검색 구조
  * 유지보수 조치 권고 자동 생성

* **Cloud**

  * AWS S3 + CloudFront 기반 파일 시스템
  * EC2 기반 Backend / AI / LLM 서버 분리
  * CI/CD Pipeline (CodeBuild, CodeDeploy, ECR)

---

## 🚀 주요 기능

### 1️⃣ AI 기반 철도 시설물 결함 탐지

* YOLO-LAF 기반 실시간 객체 탐지
* 선로, 애자, 조류 둥지 등 주요 위험 요소 탐지
* Baseline 대비 mAP 향상 및 연산량 감소

---

### 2️⃣ GIS 기반 유지보수 모니터링 UI

* 지도 기반 결함 위치 시각화
* 실시간 상태 확인
* 시설물 위치별 관리 가능

---

### 3️⃣ 규정 기반 조치 권고 자동 생성

* 탐지 결과 + JSON 메타데이터 수집
* 규정 문서 벡터 DB 검색
* LLM 기반 조치 권고 생성
* 보고서 자동 생성

---

### 4️⃣ 현장 피드백 반영 파인튜닝 파이프라인

* 사용자 오탐 수정 기능 제공
* 수정 데이터 자동 수집
* 파인튜닝 데이터 축적
* HuggingFace best.pt 자동 반영 구조

---

### 5️⃣ 유지보수 지식 응답 모델

* 규정 + 점검 기준 + 보수 사례 연계
* 보고서 형식의 구조화된 답변 생성
* 근거 기반 응답 제공

---

## 📊 기대효과

* 🔻 사고 확산 억제 (지연 확산 감소)
* 🔻 유지보수 비용 절감
* 🔺 자산 상태 가시성 향상
* 🔺 인적 오류 최소화
* 🔺 선제적 유지보수 체계 구축

특히,

* 실시간 결함 탐지
* 규정 연계 조치 자동화
* 피드백 기반 모델 고도화

를 통해 **단순 탐지를 넘어 의사결정 지원까지 확장된 구조**를 구현하였습니다.

---

## 🛠 적용 기술 스택

### Frontend

* React
* TypeScript
* Vite
* React Query
* OpenLayers

### Backend

* Kotlin
* Spring Boot
* Spring Security
* Scheduler / Worker 패턴

### AI

* YOLOv8 기반 커스텀 모델
* LWM (Adaptive Weight Pooling)
* C2f-SCConv
* EMA (FasterBlockEMA)

### LLM

* Gemini API
* RAG 구조
* 벡터 기반 규정 검색

### Cloud

* AWS EC2
* AWS S3
* AWS CloudFront
* AWS ECR
* AWS CodeBuild / CodeDeploy

---

## 🔮 향후 개선 방향

* 조치 후속 프로세스 자동 연계
* 보고서 자동 생성 기능 고도화
* 모델 경량화 및 추론 최적화
* 실시간 영상 스트리밍 기반 탐지 확장
