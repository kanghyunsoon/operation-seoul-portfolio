# Operation KOREA

> TourAPI와 AI를 활용해 관광지를 위치 기반 야외 방탈출 미션으로 전환하는 관광 게이미피케이션 서비스

Operation KOREA는 사용자가 실제 관광지를 이동하며 미션을 수행하고,  
현장 인증과 AI 채팅을 통해 최종 역사 키워드를 추론하는 위치 기반 체험형 관광 서비스입니다.

단순히 관광 정보를 조회하는 방식이 아니라,  
사용자가 직접 걷고, 찾고, 인증하고, 추리하는 흐름을 통해  
관광지를 하나의 미션형 콘텐츠로 경험할 수 있도록 기획했습니다.

<br/>

## 프로젝트 개요

| 항목 | 내용 |
| --- | --- |
| 프로젝트명 | Operation KOREA |
| 서비스 유형 | 위치 기반 야외 방탈출 / 관광 게이미피케이션 |
| 개발 기간 | 2026.05 ~ 진행 중 |
| 개발 인원 | 2명 |
| 주요 타깃 | 국내 여행자, 가족 단위 관광객, 지역 관광 콘텐츠 이용자 |
| 핵심 기능 | 지역 선택, 미션 진행, GPS 기반 도착 판정, 현장 사진 인증, AI 힌트/정답 판정 |
| 주요 기술 | Java 17, Spring Boot, MyBatis, MySQL, Spring Security, JWT, Vue 3 |

<br/>

## 팀 구성

| 이름 | 역할 | 담당 내용 |
| --- | --- | --- |
| 강형순 | Team Lead / Backend | 백엔드 REST API, RDBMS 스키마 설계, JWT 인증, TourAPI 연동, AI/Vision API 연동 |
| 홍성혁 | Frontend / Location | 지도 기반 화면, GPS 도착 판정, 지역 선택, 미션 진행 UI, 프론트엔드 API 연동 |

<br/>

## 기술 스택

### Backend

![Java](https://img.shields.io/badge/Java_17-007396?style=flat-square&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![Spring Security](https://img.shields.io/badge/Spring_Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white)
![MyBatis](https://img.shields.io/badge/MyBatis-000000?style=flat-square)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white)

### Frontend

![Vue.js](https://img.shields.io/badge/Vue_3-4FC08D?style=flat-square&logo=vuedotjs&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Axios](https://img.shields.io/badge/Axios-5A29E4?style=flat-square)

### External API / AI

![TourAPI](https://img.shields.io/badge/TourAPI-External_API-blue?style=flat-square)
![Kakao Maps](https://img.shields.io/badge/Kakao_Maps-FFCD00?style=flat-square&logo=kakao&logoColor=black)
![Tmap](https://img.shields.io/badge/Tmap-API-blue?style=flat-square)
![Gemini](https://img.shields.io/badge/Gemini_API-8E75B2?style=flat-square&logo=google&logoColor=white)
![Google Cloud Vision](https://img.shields.io/badge/Google_Cloud_Vision-4285F4?style=flat-square&logo=googlecloud&logoColor=white)

<br/>

## 주요 기능

| 기능 | 설명 |
| --- | --- |
| 회원가입 / 로그인 | Spring Security와 JWT를 활용한 인증 흐름 구현 |
| 지역 선택 | 사용자가 플레이할 작전 지역을 선택 |
| 지역별 미션 조회 | 선택한 지역의 미션 카드와 진행 상태 조회 |
| 관리자 작전 생성 | TourAPI 후보지와 AI를 활용한 미션 생성 |
| 지도 기반 미션 | Kakao Maps 기반 마커 표시, 현재 위치 확인, GPS 도착 판정 |
| 현장 사진 인증 | Google Cloud Vision API와 Gemini API를 활용한 인증 로직 |
| AI 채팅 | 힌트 질문, 가설 검증, 최종 정답 판정 |
| 클리어 리포트 | 점수, 소요 시간, 이동 거리, 실제 역사 해설 제공 |

<br/>

## 사용자 흐름

```text
회원가입 / 로그인
        ↓
지역 선택
        ↓
작전 브리핑 확인
        ↓
지도 기반 힌트 미션 진행
        ↓
GPS 도착 판정
        ↓
현장 사진 인증
        ↓
AI 채팅으로 최종 키워드 추론
        ↓
클리어 리포트 확인
```

<br/>

## 시스템 구조

```text
Vue 3 Frontend
  ├─ 지역 선택 화면
  ├─ 지도 미션 화면
  ├─ 카메라 인증 화면
  └─ AI 채팅 화면

        ↓ Axios

Spring Boot Backend
  ├─ Auth / JWT
  ├─ Region API
  ├─ Mission API
  ├─ Game Session API
  ├─ Admin Mission API
  └─ AI / Vision Service

        ↓ MyBatis

MySQL
  ├─ User
  ├─ Region
  ├─ Mission
  ├─ Game Session
  └─ AI Chat Log

        ↓ External API

TourAPI / Kakao Maps / Tmap / Gemini API / Google Cloud Vision API
```

<br/>

## 프로젝트 구조

```text
operation-seoul-portfolio
├── backend
│   ├── src/main/java/com/operation/seoul
│   │   ├── auth        # 회원가입, 로그인, JWT 인증
│   │   ├── game        # 게임 세션, AI 채팅, Vision 인증
│   │   ├── global      # 보안, CORS, 공통 설정
│   │   └── location    # 지역, 미션, 위치 판정
│   └── src/main/resources
│       └── application-example.properties
│
├── frontend
│   ├── src
│   │   ├── api
│   │   ├── components
│   │   ├── router
│   │   ├── stores
│   │   └── views
│   └── .env.example
│
├── docs
│   ├── architecture.md
│   ├── api-summary.md
│   ├── troubleshooting.md
│   └── screenshots
│
├── schema.sql
├── README.md
└── .gitignore
```

<br/>

## 핵심 구현 내용

### 1. Spring Security + JWT 인증

사용자 로그인 후 JWT를 발급하고,  
보호된 API 요청에서는 JWT 필터를 통해 사용자 인증 정보를 검증하도록 구현했습니다.

- 회원가입 / 로그인 API 구현
- JWT 발급 및 검증
- 인증 필요 API 보호
- 현재 로그인 사용자 정보 해석

<br/>

### 2. MyBatis 기반 RDBMS 연동

JPA 대신 MyBatis를 사용해 SQL을 직접 작성하고,  
회원, 미션, 게임 세션, AI 채팅 로그 등 서비스 데이터를 MySQL에 저장하도록 구성했습니다.

- MySQL 테이블 설계
- MyBatis Mapper 작성
- CRUD API 구현
- 초기 테이블 생성을 위한 `schema.sql` 구성

<br/>

### 3. TourAPI 기반 관광지 후보 조회

TourAPI 공공데이터를 활용해 지역별 관광지 후보를 조회하고,  
AI 미션 생성의 원천 데이터로 사용할 수 있도록 서버 로직을 구성했습니다.

- 지역 기반 관광지 후보 조회
- 관광지 좌표 / 설명 데이터 활용
- 관리자 미션 생성 흐름과 연동

<br/>

### 4. AI / Vision API 연동

Google Cloud Vision API를 통해 사용자의 현장 인증 이미지를 분석하고,  
Gemini API를 활용해 힌트 제공, 정답 판정, 클리어 리포트 생성 흐름을 구성했습니다.

- 현장 인증 사진 분석
- AI 힌트 응답 생성
- 사용자 정답 키워드 판정
- 클리어 후 역사 해설 생성

<br/>

### 5. 지도 기반 미션 진행

Kakao Maps와 GPS 정보를 활용해  
사용자의 현재 위치, 미션 마커, 도착 여부를 화면에서 확인할 수 있도록 구성했습니다.

- 지도 마커 표시
- 현재 위치 확인
- GPS 기반 도착 판정
- 미션 진행 상태 연동

<br/>

## 주요 API

| Method | Endpoint | 설명 |
| --- | --- | --- |
| `POST` | `/api/v1/auth/register` | 회원가입 |
| `POST` | `/api/v1/auth/login` | 로그인 및 JWT 발급 |
| `GET` | `/api/v1/regions/cards` | 지역별 작전 카드 조회 |
| `GET` | `/api/v1/regions/{regionId}/missions` | 지역별 미션 목록 조회 |
| `POST` | `/api/v1/sessions/{missionId}/vision` | 현장 사진 인증 |
| `POST` | `/api/v1/sessions/{missionId}/chat/stream` | AI 채팅 및 정답 판정 |
| `GET` | `/api/v1/sessions/{missionId}/clear-report` | 클리어 리포트 조회 |
| `GET` | `/api/v1/admin/missions/region-candidates` | 관리자 후보지 조회 |
| `POST` | `/api/v1/admin/missions/generate-selected` | 선택 후보지 기반 AI 작전 생성 |

<br/>

## 실행 방법

### Backend

`application-example.properties`를 복사해 로컬 설정 파일을 생성합니다.

```powershell
Copy-Item backend/src/main/resources/application-example.properties backend/src/main/resources/application-local.properties
```

`application-local.properties`에 DB 및 API Key 값을 입력합니다.

```properties
DB_URL=jdbc:mysql://localhost:3306/operation_seoul
DB_USERNAME=root
DB_PASSWORD=your_password

JWT_SECRET=your_jwt_secret

TOUR_API_KEY=your_tour_api_key
KAKAO_API_KEY=your_kakao_api_key
TMAP_API_KEY=your_tmap_api_key
GEMINI_API_KEY=your_gemini_api_key
GOOGLE_VISION_CREDENTIAL_PATH=your_google_vision_json_path
```

Backend 실행:

```powershell
cd backend
java -classpath .\gradle\wrapper\gradle-wrapper.jar org.gradle.wrapper.GradleWrapperMain bootRun
```

<br/>

### Frontend

`.env.example`을 복사해 로컬 환경 파일을 생성합니다.

```powershell
Copy-Item frontend/.env.example frontend/.env
```

Frontend 실행:

```powershell
cd frontend
npm install
npm run dev
```

<br/>

## 보안 및 공개 저장소 처리

본 저장소는 포트폴리오 제출용 공개 저장소입니다.  
따라서 실제 API Key, DB 비밀번호, JWT Secret, Google Cloud 인증 JSON은 포함하지 않습니다.

공개 저장소에는 아래 파일만 예시 형태로 포함합니다.

```text
application-example.properties
.env.example
```

실제 실행에 필요한 민감 정보는 로컬 환경에서 별도로 설정해야 합니다.

<br/>

## 트러블슈팅

### 1. 외부 API Key 관리 문제

초기에는 외부 API Key를 로컬 설정에 직접 관리했지만,  
공개 저장소 전환을 고려해 예시 설정 파일과 실제 설정 파일을 분리했습니다.

이를 통해 API Key가 Git에 포함되지 않도록 관리했습니다.

<br/>

### 2. MyBatis 기반 SQL 관리

ORM이 SQL을 자동으로 생성하는 방식 대신 MyBatis를 사용하면서,  
쿼리 작성과 테이블 구조를 직접 이해해야 했습니다.

이를 통해 요청 데이터가 Controller, Service, Mapper, DB를 거쳐  
응답으로 반환되는 백엔드 흐름을 더 명확히 이해할 수 있었습니다.

<br/>

### 3. 여러 외부 API 연동

TourAPI, Kakao Maps, Tmap, Gemini API, Google Cloud Vision API를 함께 사용하면서  
API별 응답 구조와 예외 상황이 다르다는 점을 확인했습니다.

이에 따라 서버 로직에서 응답 데이터 정제, null 처리, 예외 처리를 분리해 관리했습니다.

<br/>

## 배운 점

- Spring Boot 기반 API 서버의 기본 흐름을 프로젝트 단위로 경험했습니다.
- MyBatis를 사용하며 SQL과 RDBMS 테이블 설계의 중요성을 체감했습니다.
- JWT 인증 흐름을 직접 구현하며 인증/인가 구조를 이해했습니다.
- 여러 외부 API를 하나의 서비스 흐름에 연결하며 예외 처리의 중요성을 배웠습니다.
- AI API를 단순 호출하는 것이 아니라, 서비스 기능 안에서 어떤 역할로 연결할지 고민했습니다.

<br/>

## 향후 개선 방향

- 미션별 리뷰 기능 추가
- 미션 찜 / 즐겨찾기 기능 추가
- 사용자 클리어 기록 기반 랭킹 기능
- 다국어 관광정보 API 연동
- 무장애 관광정보 API 기반 배리어프리 미션 확장
- 지자체용 관광 인사이트 대시보드 확장

<br/>

## Repository Purpose

이 저장소는 채용 및 포트폴리오 제출을 위해 정리한 공개용 저장소입니다.

기존 작업 저장소에서 민감 정보와 불필요한 실험 코드를 제거하고,  
프로젝트 구조, 핵심 구현 내용, 실행 방법을 확인할 수 있도록 정리했습니다.