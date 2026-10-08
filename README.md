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

### MoneyToad · 돈꺼비 | 소비 분석·절약 서비스

`SSAFY 팀 프로젝트 · 2025` `Backend` `후속 개인 개선 2026.09~10`

[**데모**](https://moneytoad-portfolio.pages.dev/) · [포트폴리오 저장소](https://github.com/rladbstn1000/MoneyToad-Portfolio) · [원본 팀 저장소](https://github.com/rladbstn1000/MoneyToad) · [기여 구분](https://github.com/rladbstn1000/MoneyToad-Portfolio/blob/main/docs/portfolio/contribution-boundary.md)

- **문제:** 소비 내역과 예산을 비교해 지출 누수를 파악.
- **구현:** JWT·Redis로 토큰 재발급과 로그아웃을 처리하고, 월별·카테고리별 SQL 집계와 AI 분석 결과를 소비 기준 API에 연결.
- **후속 개선:** 예산·카드 객체의 소유권 검증, Redis 데모 세션의 토큰 회전과 재사용 시 폐기, 실제 MySQL·Redis·Chromium E2E 검증 환경 구성.

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

- **MoneyToad:** [JWT·Redis 토큰 관리](https://github.com/rladbstn1000/MoneyToad/commit/cdf9d6f9dc9281f7d26bc4d6b72987e4a82c1b42) · [소비 내역·SQL 집계](https://github.com/rladbstn1000/MoneyToad/commit/42c0293ed70ef9149777be788105596c704ce9a3) · [AI 분석 결과 연동](https://github.com/rladbstn1000/MoneyToad/commit/625b8b6bf63dc29e8bc780749c7f2cd555d5349e)
- **ETCH:** [통합검색 API](https://github.com/rladbstn1000/ETCH/commit/fdc85c110acef6ccaaeaa9dcc2775ba94ee48fb8) · [검색 페이지네이션](https://github.com/rladbstn1000/ETCH/commit/64a70777109c1af31ca2e9c601a7d9ce64b0168a) · [검색 인덱스 갱신 개선](https://github.com/rladbstn1000/ETCH/commit/43db667002518d71816d5db71b471efb80282dec)
- **DO-DREAM:** [인증 API](https://github.com/rladbstn1000/DO-DREAM/commit/ef5f8ce1d6417c11938a68b786b17af2e9f92a5c) · [RAG 검색 결과 재정렬](https://github.com/rladbstn1000/DO-DREAM/commit/ccdc99bb21ff8637ad341913cb96c0aaec22ac0e) · [퀴즈 채점](https://github.com/rladbstn1000/DO-DREAM/commit/826c59d7c59e803023eee145f78bb767202f9704) · [최신 제출 기준 통계](https://github.com/rladbstn1000/DO-DREAM/commit/52c27c9e8a529cb5f31674eee307ca5da23577c9)

</details>
