# ARUBI (NoDam) — AI 여행 플래너

> 최소한의 정보 입력만으로 AI가 최적의 여행 일정을 자동으로 만들어주는 여행 플래너, **ARUBI**입니다.

---

## 프로젝트 소개

<img width="213" height="76" alt="스크린샷 2026-06-16 오후 5 27 38" src="https://github.com/user-attachments/assets/2bc92b33-04ca-4876-80e6-3fe7f2a03682" />

<!-- TODO: front 캡처 화면 삽입 -->

**ARUBI**는 사용자가 최소 정보만 입력하면, AI가 검증된 장소들을 바탕으로 맞춤형 여행 일정을 생성해주는 서비스입니다.

- **필수 입력** : 여행 국가·도시, 인원, 여행 날짜(시작·종료)
- **선택 입력** : 숙소, 가고 싶은 싶은 장소, 항공편(출발·도착), 여행 스타일, 예산

---

## 주요 기능

### AI 일정 자동 생성
- 사용자의 최소한의 정보를 통해 AI가 여행 일정을 생성합니다.
- 날짜별 필수 장소(공항, 숙소) 배정 → 후보 장소 조회 → 가중치 기반 추천 → Route 정보 조회 순으로 일정을 구성합니다.
- 완성된 여행 일정은 지도와 같이 확인할 수 있습니다.

<img width="320" height="700" alt="스크린샷 2026-10-14 오후 8 24 12" src="https://github.com/user-attachments/assets/5456f3c5-2bec-409b-a9df-12c2bc062dda" />

<img width="320" height="700" alt="스크린샷 2026-10-14 오후 8 18 44" src="https://github.com/user-attachments/assets/4e799808-1c05-47e2-97ba-8a0b4ef7e901" />


### 일정 공유 / 실시간 공동 편집
- 생성된 일정은 추가 / 수정 / 삭제 가능합니다.
- 동행자를 초대해 여행 일정 공유합니다.
- 공유된 일정은 동행자와 동시에 편집할 수 있습니다.
<img width="320" height="700" alt="스크린샷 2026-10-14 오후 8 21 06" src="https://github.com/user-attachments/assets/3f838b52-1d89-4102-85db-9795d770df74" />


### AI 장소 추천
- 맘에 들지 않는 장소는 AI에게 다시 추천 받을 수 있습니다.
- 지역·예산·계절·테마·날씨 가중치를 통해 장소를 추천합니다.
<img width="320" height="700" alt="스크린샷 2026-10-14 오후 8 25 05" src="https://github.com/user-attachments/assets/99efa447-b621-40ad-87ff-bbadd4b9b7d0" />

### 장소 DB 파이프라인
- AI 일정 생성에 사용되는 장소들은 모두 미리 선별된 장소들입니다.
- 크롤링 → 정제 → LLM → DB 반영 파이프라인을 통해 장소 DB를 직접 구성하여 운영됩니다
<img width="850" height="150" alt="crawling_pipeline_large" src="https://github.com/user-attachments/assets/56e25f3b-095d-49c3-92f6-57099def1b39" />

---

## 기술 스택

### Frontend
| 구분 | 기술 |
|------|------|
| Language / Framework | TypeScript, React, Vite |
| 상태 관리 | Zustand, TanStack Query |
| Form / 검증 | React Hook Form, Zod |
| HTTP / UI | Axios, Framer Motion |

### Backend
| 구분 | 기술 |
|------|------|
| Language / Framework | Java 21, Spring Boot 3.5.7 |
| Security | Spring Security, JWT |
| DB | JPA (Hibernate), QueryDSL, MySQL 8.0 |
| 장소 DB 파이프라인 | FastAPI, LLM |
| 인증 | Google · Kakao · Naver OAuth |
| 외부 연동 | Google Places(장소) · Google Routes · NAVITIME(경로), AirLabs(항공), Xotelo(숙소), Open-Meteo(날씨), Microsoft Translator(번역) |
| Infra / CI-CD | Docker, GitHub Actions, AWS EC2 |

---

## ERD

<!-- TODO: 최신 ERD 이미지 삽입 -->

---

## 팀원

**TEAM. NODAM**

| Frontend | Backend |
|------|------|
| 육나윤 | 이권희 |
| 민도현 | 최진솔 |
