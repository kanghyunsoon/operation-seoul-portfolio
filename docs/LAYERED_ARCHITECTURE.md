# 계층구조 설명

## 1. 패키지 구조

```text
backend/src/main/java/com/operation/korea
|-- OperationKoreaApplication.java
|-- auth
|   |-- controller
|   |-- domain
|   |-- dto
|   |-- mapper
|   |-- security
|   `-- service
|-- region
|   |-- controller
|   |-- domain
|   |-- mapper
|   `-- service
|-- mission
|   |-- client
|   |-- controller
|   |-- domain
|   |-- dto
|   |-- mapper
|   `-- service
|-- session
|   |-- controller
|   |-- domain
|   |-- dto
|   |-- mapper
|   `-- service
`-- global
    |-- config
    |-- dto
    `-- exception
```

## 2. 계층별 책임

| 계층 | 패키지 | 책임 |
| --- | --- | --- |
| Controller | `**/controller` | HTTP 요청/응답, path/query/body 검증 진입점 |
| Service | `**/service` | 비즈니스 규칙, 트랜잭션 경계, 외부 API와 DB 호출 조합 |
| Mapper Interface | `**/mapper` | MyBatis mapper 계약 정의 |
| Mapper XML | `src/main/resources/mapper` | SQL 정의, resultMap 관리 |
| Domain | `**/domain` | DB 테이블과 대응되는 도메인 객체 |
| DTO | `**/dto` | API 요청/응답 전용 객체 |
| Client | `mission/client` | TourAPI, Gemini, Vision, Tmap 등 외부 API 연동 지점 |
| Global | `global` | 보안, 공통 응답, 예외 처리, 설정 |

## 3. 의존 방향

<img src="docs/images/system_architecture.png" alt="의존방향" width="100%">

Controller는 Mapper를 직접 호출하지 않는다. 외부 API 호출도 Controller에서 처리하지 않고 Service를 거쳐 Client로 위임한다. 이 구조를 유지하면 TourAPI/Gemini/Vision 연동부를 mock으로 교체해도 핵심 도메인 로직 테스트가 가능하다.
