# REST API 설계도

## 1. REST API 흐름

<img src="docs/images/REST_API_flow.png" alt="RESTAPI" width="100%">

## 2. 주요 API 목록

| Method | Path | 인증 | 설명 |
| --- | --- | --- | --- |
| POST | `/api/v1/auth/register` | 공개 | 회원가입 |
| POST | `/api/v1/auth/login` | 공개 | 로그인 및 JWT 발급 |
| GET | `/api/v1/regions` | 선택 | 지역 목록 조회 |
| GET | `/api/v1/regions/cards?areaCode={code}` | 선택 | 지역별 작전 카드 조회 |
| GET | `/api/v1/regions/{regionId}/missions` | 필요 | 지역 미션 목록 조회 |
| POST | `/api/v1/missions/{missionId}/arrive` | 필요 | GPS 도착 판정 |
| POST | `/api/v1/sessions/{missionId}/vision` | 필요 | 현장 사진 인증 |
| POST | `/api/v1/sessions/{missionId}/chat` | 필요 | AI 힌트/정답 판정 |
| GET | `/api/v1/sessions/{missionId}/clear-report` | 필요 | 클리어 리포트 조회 |
| GET | `/api/v1/admin/missions/region-candidates` | 관리자 | TourAPI 지역 후보 조회 |
| POST | `/api/v1/admin/missions/generate-selected` | 관리자 | 선택 후보 기반 AI 작전 생성 |

## 3. 인증/권한 처리

<img src="docs/images/03.png" alt="인증권한" width="100%">

## 4. 작전 생성 흐름

<img src="docs/images/04.png" alt="작전생성" width="100%">

## 5. 미션 수행 흐름

<img src="docs/images/05.png" alt="미션수행" width="100%">
