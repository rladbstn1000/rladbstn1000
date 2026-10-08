# 김윤수 | Backend Developer

Java · Spring Boot를 중심으로 **인증, 검색, 학습 데이터 API**를 개발합니다.
팀 프로젝트가 끝난 뒤에도 데이터 정합성과 조회 성능 문제를 직접 재현하고 개선했습니다.

## Core Stack

| 분야 | 기술 |
| --- | --- |
| Backend | Java · Spring Boot · Spring Security · Spring Data JPA |
| Data | MySQL · Redis · Elasticsearch |
| AI 서비스 개발 | Python · FastAPI · LangChain · ChromaDB |

## Featured Projects

> 데모는 로그인 없이 샘플 데이터로 둘러보는 체험판입니다.

### [MoneyToad · 돈꺼비](https://github.com/rladbstn1000/MoneyToad-Portfolio) — 소비 분석·절약 서비스

[체험판](https://moneytoad-portfolio.pages.dev/) · [백엔드 사례](https://github.com/rladbstn1000/MoneyToad-Portfolio/blob/main/docs/portfolio/backend-cases.md) · [담당 범위와 원본 기여 기록](https://github.com/rladbstn1000/MoneyToad-Portfolio/blob/main/docs/portfolio/contribution-boundary.md)

- **원래 담당:** Spring Boot 인증·토큰 관리, 소비 내역·예산 API, 월별·카테고리별 SQL 집계, AI 분석 결과 연동.
- **후속 개선:** 예산·카드 소유권 검사와 회귀 테스트, 서버 연동 데모의 Redis 원자적 토큰 회전·재사용 폐기, 기존 화면을 살린 정적 체험판 전환.
- **체험 범위:** 공개 링크는 브라우저 메모리 기반 샘플입니다. 실제 백엔드 구현과 서버 연동 검증은 저장소에서 구분해 확인할 수 있습니다.

### ETCH | IT 취업 준비 통합 플랫폼

`팀 프로젝트 · 2025.07~08 · 6명` `백엔드 리드` `후속 개인 개선 2026.09~10`

[**데모**](https://etch-showcase.pages.dev/) · [저장소](https://github.com/rladbstn1000/ETCH) · [개발 과정](https://etch-showcase.pages.dev/process) · [상세 원고](https://github.com/rladbstn1000/ETCH/blob/master/docs/portfolio-kit/ETCH.md)

- **문제:** 채용공고·뉴스·프로젝트를 한곳에서 탐색.
- **구현:** Elasticsearch 통합검색 API·조건 필터·페이지네이션. 프로젝트 변경·좋아요·조회수를 DB 커밋 후 검색 인덱스에 반영하고, 비공개·삭제 프로젝트를 색인에서 제거.
- **후속 개선:** 색인 반영 실패에 대비해 outbox와 영속 재시도를 도입해 수동 재색인 없이 검색 상태를 복구. 목록 조회의 JDBC 실행을 **102회 → 2회**로 감소(서로 다른 작성자 100건, 합성 데이터 기준).

### DO-DREAM | 시각장애 학생을 위한 AI 음성 학습 플랫폼

`팀 프로젝트 · 2025.10~11 · 6명` `Backend` `후속 개인 개선 2026`

[**데모**](https://rladbstn1000.github.io/DO-DREAM/) · [저장소](https://github.com/rladbstn1000/DO-DREAM) · [코드 리뷰 문서](https://github.com/rladbstn1000/DO-DREAM/blob/main/docs/portfolio/18-portfolio-code-review.md)

- **문제:** 학습 자료 기반 질의응답과 학습 결과 확인을 지원.
- **구현:** JWT·Redis 인증, LangChain·ChromaDB 기반 RAG 질의응답, AI 퀴즈 생성·채점 및 성적 통계. 퀴즈별 최신 제출만 정답률에 반영해 반복 풀이에 따른 중복 집계를 방지.
- **후속 개선:** Refresh Token 회전과 객체 단위 접근 권한 검사, 퀴즈 제출 멱등성으로 같은 제출의 중복 채점 방지. 통계 쿼리 수를 **85개 → 9개**로 감소(합성 데이터 기준).

<details>
<summary>구현 코드와 기여 기록</summary>

아래는 각 팀 프로젝트에서 직접 작성한 코드의 변경 기록입니다.

- **MoneyToad:** [예산 소유권 검사](https://github.com/rladbstn1000/MoneyToad-Portfolio/blob/main/be/src/main/java/com/potg/don/budget/service/BudgetService.java) · [demo 원자적 회전](https://github.com/rladbstn1000/MoneyToad-Portfolio/blob/main/be/src/main/resources/redis/demo-session-rotate.lua) · [월별·카테고리 집계](https://github.com/rladbstn1000/MoneyToad-Portfolio/blob/main/be/src/main/java/com/potg/don/transaction/repository/TransactionRepository.java) · [원래 역할과 후속 개선 구분](https://github.com/rladbstn1000/MoneyToad-Portfolio/blob/main/docs/portfolio/contribution-boundary.md)
- **ETCH:** [통합검색 API](https://github.com/rladbstn1000/ETCH/commit/fdc85c110acef6ccaaeaa9dcc2775ba94ee48fb8) · [검색 페이지네이션](https://github.com/rladbstn1000/ETCH/commit/64a70777109c1af31ca2e9c601a7d9ce64b0168a) · [검색 인덱스 갱신 개선](https://github.com/rladbstn1000/ETCH/commit/43db667002518d71816d5db71b471efb80282dec)
- **DO-DREAM:** [인증 API](https://github.com/rladbstn1000/DO-DREAM/commit/ef5f8ce1d6417c11938a68b786b17af2e9f92a5c) · [RAG 검색 결과 재정렬](https://github.com/rladbstn1000/DO-DREAM/commit/ccdc99bb21ff8637ad341913cb96c0aaec22ac0e) · [퀴즈 채점](https://github.com/rladbstn1000/DO-DREAM/commit/826c59d7c59e803023eee145f78bb767202f9704) · [최신 제출 기준 통계](https://github.com/rladbstn1000/DO-DREAM/commit/52c27c9e8a529cb5f31674eee307ca5da23577c9)

</details>
