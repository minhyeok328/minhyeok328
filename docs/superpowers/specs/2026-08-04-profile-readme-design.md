# GitHub Profile README Design

## 1. 목적

`README.md`를 채용 담당자와 기술 면접관이 빠르게 이해할 수 있는 개발자 소개 페이지로 재구성한다. 단순한 기술 배지와 프로젝트 나열보다 다음 세 가지를 우선한다.

1. 희망 직무인 AI·LLM 풀스택 개발자 정체성
2. 실제 코드와 커밋으로 확인되는 프론트엔드 강점
3. 데이터 수집에서 ML, LLM, 웹 서비스로 확장된 성장 과정

## 2. 핵심 포지셔닝

### 최상위 정체성

**프론트엔드 강점을 가진 AI/LLM 풀스택 개발자**

### 헤드라인

> **AI · LLM Full-Stack Developer**<br>
> 프론트엔드 강점을 기반으로 LLM, API, 데이터 흐름을 연결해 사용자에게 닿는 AI 서비스를 만듭니다.

### 포지셔닝 원칙

- 프론트엔드 개발자로만 한정하지 않는다.
- 모든 기술의 전문가처럼 표현하지 않는다.
- LLM·RAG를 핵심 전문 방향으로 둔다.
- React·TypeScript와 서비스 통합을 현재의 가장 강한 실무 역량으로 제시한다.
- Django·FastAPI·DB는 풀스택 확장 역량으로, 비동기 처리·배포는 팀 시스템과의 연동 및 구조 이해 경험으로 보여준다.
- 팀 전체 성과와 서민혁의 직접 기여를 항상 구분한다.

## 3. 독자와 읽기 흐름

### 1순위 독자

- 채용 담당자
- 기술 면접관

### 첫 10초 안에 전달할 내용

1. AI/LLM 풀스택 개발자를 지향한다.
2. 프론트엔드 구조와 서비스 통합이 가장 강한 역량이다.
3. LangGraph·RAG부터 API·UI·QA까지 연결한 경험이 있다.
4. 파이널 프로젝트에서 프론트엔드 오너 역할을 수행했다.

## 4. 전체 정보 구조

1. Hero
2. About Me
3. Core Strengths
4. Flagship Project — HumouR
5. Project Journey — From Data to AI Service
6. Tech Stack — 기술 매트릭스
7. How I Build
8. Other Work
9. GitHub Activity

콘텐츠 비중은 HumouR 약 50%, 3·4차 약 35%, 1·2차 약 15%로 구성한다.

## 5. 섹션별 설계

### 5.1 Hero

- 현재의 어두운 GitHub 테마와 중앙 정렬 구조는 유지한다.
- 장식용 배너보다 직무 정체성과 한 문장 설명을 먼저 읽히게 한다.
- 헤드라인은 `AI · LLM Full-Stack Developer`로 고정한다.
- 보조 문장은 데이터·모델·API·UI의 연결 능력을 강조한다.

### 5.2 About Me

다음 내용을 3개의 짧은 문단으로 작성한다.

> 안녕하세요. LLM 기능을 데모에 머물게 하지 않고 실제 서비스의 사용자 흐름으로 연결하는 개발자 서민혁입니다.

> 데이터·모델·백엔드·사용자 화면으로 이어지는 전체 흐름을 경험했으며, 특히 LangGraph·RAG 파이프라인과 프론트엔드·서비스 통합을 직접 구현해 왔습니다.

> 최근에는 AI 채용 지원 플랫폼 HumouR의 프론트엔드 오너로서 애플리케이션 구조, API 계약, 인증·세션 경계, 비동기 상태, QA·보안 안정화를 담당했습니다.

### 5.3 Core Strengths

- **LLM Application:** LangGraph, RAG, 구조화 출력, 검색·생성 파이프라인
- **Frontend Architecture:** React, TypeScript, TanStack Query, Zod
- **Full-Stack Integration:** Django, FastAPI, REST API, MySQL, SQLite
- **Service Reliability:** 인증·CSRF, 오류 처리, 요청 수명주기, 테스트·QA
- **Collaboration:** Git·PR 워크플로, 인터페이스 계약, 기술 문서화

### 5.4 Flagship Project — HumouR

#### 서비스 소개

> HR 전담 인력이 부족한 조직을 위한 AI 채용 운영 플랫폼. AI가 합격 여부를 대신 결정하지 않고, 지원서 정보와 확인 질문을 통해 담당자의 일관된 판단을 지원합니다.

#### 팀이 구축한 시스템

React·Django·Celery·LangGraph·Pinecone·RunPod를 결합하고 저장소 기준 AWS 배포 자동화까지 구성해 회사 정보, JD, 평가 체크리스트, 지원서 분석, 리포트, 면접 질문, 제한 공유와 문서 챗을 하나의 흐름으로 연결한 팀 프로젝트임을 명시한다.

#### My Role — Frontend Owner

- 프론트엔드 CODEOWNER로서 React·TypeScript 애플리케이션의 구조·통합·품질 기준 주도
- Axios·CSRF 요청 계층부터 도메인 API Client, Zod 계약, Adapter, TanStack Query로 이어지는 데이터 흐름 설계
- 일반 계정과 제한 API Key 세션의 권한·캐시 격리
- 인증 만료 처리, 요청 취소, 오류 정제, 캐시 정리 등 요청 수명주기 안정화
- JD·지원서·분석 리포트·외부 공유·문서 챗을 가로지르는 API 연동, 상태 흐름 및 통합 검증
- 프론트엔드 테스트·검증 체계 구축과 확장에 기여. 팀 저장소 기준 테스트 파일 53개(Vitest 51개, Playwright 2개)와 검증 스크립트 16개로 API 계약, 상태 변화, 인증·보안, 접근성 검증
- 코드·API 인터페이스 정의서·운영 문서의 정합성 관리

#### 기술 경계

- **직접 기여:** React 19 · TypeScript · Axios · TanStack Query · Zod · Ant Design · Vitest · MSW · Playwright
- **팀 시스템과 연동:** Django API · Celery 비동기 상태 · LangGraph/Pinecone 분석 결과 · AWS 배포 구성

#### 핵심 메시지

> AI 기능의 완성도는 모델 응답만으로 결정되지 않습니다. 명확한 API 계약, 격리된 인증 상태, 예측 가능한 오류 처리와 반복 가능한 검증 체계가 함께 갖춰져야 실제 서비스가 됩니다.

### 5.5 Project Journey — From Data to AI Service

모든 프로젝트는 팀 프로젝트로 표시하고, `My Contribution` 열에는 직접 기여만 작성한다.

| Stage | Project | My Contribution | Growth |
| --- | --- | --- | --- |
| **01 · Data Integration** | [차량 운영·관리 비용 계산 시스템](https://github.com/minhyeok328/1st_project) | 공공 연비 API 수집·JSON 파싱, CSV 로드·파싱, 비용 모델과 데이터 흐름 문서화 | 외부 데이터를 서비스 입력값으로 연결 |
| **02 · ML Experimentation** | [신용카드 고객 이탈 분석](https://github.com/minhyeok328/2nd_project) | 전처리 탐색 노트북, Unknown 소득 보완을 위한 XGBoost 그룹 분류 실험, EDA 시각화·Streamlit 프로토타입 | 모델 실험의 한계를 확인하고 사용자에게 전달할 분석으로 확장 |
| **03 · LLM & RAG** | [PICKLE 맛집 추천 챗봇](https://github.com/minhyeok328/3rd_project) | LangGraph 파이프라인, OpenAI strict JSON Schema 슬롯 추출, SQLite 임베딩 검색 커넥터 연동, Streamlit UI, 3단계 내부 평가 | LLM 응답을 실제 데이터와 근거에 연결 |
| **04 · Web Integration** | [LG Home AI 가전 상담](https://github.com/minhyeok328/4th_project) | Django·Tailwind 기반 주요 화면, 검색·필터·찜·채팅 API 연동, 오류·로딩·모바일 UX 개선 | LLM 기능을 계정·대화방 기반 Django 애플리케이션의 사용자 흐름에 통합 |
| **05 · AI Full-Stack** | [HumouR](https://github.com/minhyeok328/Final_project) | 프론트엔드 CODEOWNER, API 계약·인증·상태·테스트·QA 구조화 | 인증·비동기 상태·오류·검증을 다루는 애플리케이션 구조로 확장 |

프로젝트 상세 설명에는 비교적 근거가 명확한 3차 내부 평가 결과만 짧게 포함한다.

- 3차: 내부 자동 생성 50개 평가셋에서 통과율 `46% → 82%`, 타깃 포함률 `52% → 96%`

2차 소득 그룹 실험 수치는 ID 피처가 포함된 라벨 보유 데이터의 내부 탐색 결과이고 Unknown 고객의 정답 및 운영 통합이 검증되지 않았으므로 프로필 README에서는 생략한다.

### 5.6 Tech Stack — B안 기술 매트릭스

사용자가 시각 비교에서 선택한 B안이다. 배지 벽 대신 4행 매트릭스로 구성해 주력 기술과 함께 사용한 기술을 5초 안에 구분하도록 한다.

`Primary`는 반복적으로 직접 코드를 작성하고 검증한 현재의 중심 기술, `Project experience`는 이전 프로젝트의 직접 사용 또는 팀 시스템 경계에서의 연동 경험을 뜻한다. 팀 기술 스택에 존재했을 뿐 실제로 다루지 않은 기술은 표기하지 않는다.

| Area | Primary | Project experience |
| --- | --- | --- |
| **Frontend** | React · TypeScript · Axios · TanStack Query · Zod | JavaScript · Tailwind CSS · Ant Design · Django Templates · Streamlit |
| **LLM Application** | LangGraph · LangChain · RAG · OpenAI API · Structured Output | Pinecone 연동 |
| **Backend & Data** | Python · Django · pandas · scikit-learn · XGBoost | FastAPI 소비 · MySQL/SQLite 연동 · Celery/MLflow 경계 |
| **Quality & Delivery** | Vitest · Testing Library · MSW · Playwright · Git/GitHub | Docker · GitHub Actions · AWS 배포 구성 이해 |

기술 매트릭스 아래에 추가 배지를 중복 배치하지 않는다.

### 5.7 How I Build

- **Connect the whole flow:** 데이터 수집, 모델, API, 상태 관리, UI를 하나의 사용자 흐름으로 연결한다.
- **Define contracts:** 프론트엔드와 백엔드 사이의 요청·응답 계약을 명확히 정의하고 런타임에서 검증한다.
- **Design failure states:** 로딩·오류·인증 만료·요청 취소·비동기 처리 상태를 정상 흐름과 함께 설계한다.
- **Verify repeatedly:** 내부 평가·정적 QA·자동 테스트 등 프로젝트 성격에 맞는 방식으로 반복 검증한다.
- **Document decisions:** 코드와 인터페이스 문서를 동기화해 팀원이 같은 기준으로 작업할 수 있게 한다.

### 5.8 Other Work

기존 `codex_subagent`는 핵심 프로젝트 목록에서 제외하고 하단의 작은 항목으로 유지한다. 에이전트 오케스트레이션 학습과 문서 검증 자동화라는 성격만 짧게 소개한다.

### 5.9 GitHub Activity

- 최하단에 배치한다.
- 동적 통계 카드는 최대 2개만 유지한다.
- 통계가 핵심 프로젝트와 개발 역량보다 먼저 보이지 않게 한다.

## 6. 시각 디자인 원칙

- 한국어 본문과 영어 섹션명을 병행한다.
- GitHub 다크 테마에서 읽기 쉬운 기본 Markdown과 최소한의 HTML만 사용한다.
- 긴 배지 나열, 장식용 구분선, 반복 설명을 줄인다.
- 프로젝트 링크는 모두 사용자가 지정한 개인 저장소를 사용한다.
- HumouR는 상세 사례, 1~4차는 비교 가능한 성장 표로 표현한다.
- 모바일에서 넓은 표가 읽히지 않을 경우 HTML `<br>`로 셀 길이를 줄이고 프로젝트 설명은 표 아래 짧은 목록으로 보완한다.
- 공개 연락처는 추가하지 않고 GitHub 프로필 링크만 사용한다.

## 7. 사실성 가드레일

### 공통

- 팀 프로젝트를 단독 개발로 표현하지 않는다.
- 커밋 수를 코드 기여율로 환산하지 않는다.
- 저장소에 테스트·배포 설정이 없으면 완료된 운영 경험처럼 쓰지 않는다.

### 1차

- 완전한 TCO 또는 개인별 정확한 비용 예측이라고 표현하지 않는다.
- API·CSV 파싱 외 전체 서비스 단독 구현을 주장하지 않는다.
- 차량 가격은 조회 정보이며 계산된 월간·연간 운영비 합계에 포함되지 않는다.
- DB 적재기·조회 모듈 전체를 개인 구현으로 귀속하지 않는다.

### 2차

- 정확한 소득 구간을 90% 예측했다고 표현하지 않는다.
- 전체 ETL·FastAPI·MLflow 인프라를 개인 기여로 귀속하지 않는다.
- 소득 그룹 실험을 고객 이탈 예측 모델 성과로 표현하지 않는다.
- 성능 수치는 라벨 보유 데이터의 내부 탐색 평가이며 Unknown 데이터 정확도나 운영 통합 결과가 아니다.

### 3차

- 전용 벡터 DB, 프로덕션 배포, 실사용 정확도 97.25%를 주장하지 않는다.
- 저장된 DB 없이 즉시 실행 가능하다고 쓰지 않는다.
- 데이터 수집·DB·Kakao Map을 개인 기여로 귀속하지 않는다.
- SQLite 임베딩 검색 로직 자체, FastAPI 서버 완성, 영속적 멀티사용자 대화, 엄밀한 교집합 검색을 개인 성과로 주장하지 않는다.

### 4차

- LangGraph·Pinecone RAG 전체를 개인 구현으로 소개하지 않는다.
- AI 전체 정확도 100%, 자동 테스트 완료, 프로덕션 운영을 주장하지 않는다.
- QA 문서는 정적 코드 분석이므로 실제 브라우저·모바일 기기 검증 완료로 표현하지 않는다.
- Django JSON 엔드포인트를 DRF 기반 REST 백엔드 전체 구현으로 확대하지 않는다.
- 저장소에 SQLite DB와 Pinecone 인덱스가 포함되어 즉시 재현 가능하다고 쓰지 않는다.

### 파이널

- AI·백엔드·데이터·인프라 전체를 개인 개발로 소개하지 않는다.
- EXAONE LoRA를 독자 파운데이션 모델 개발로 표현하지 않는다.
- 노트북 평가 수치를 운영 SLA나 공정성 인증으로 확대하지 않는다.
- 현재 공개 서비스 운영, 완전한 엔터프라이즈 보안, 결제·RBAC·감사 로그를 주장하지 않는다.
- 채용 합격 여부를 AI가 자동 결정하는 서비스로 표현하지 않는다.
- 테스트 파일 53개와 검증 스크립트 16개는 팀 저장소 총량이며 개인 작성량이나 테스트 케이스 수로 표현하지 않는다.
- 백엔드 자동 테스트나 CI 테스트 품질 게이트가 있다고 주장하지 않는다.
- 앱 수준 인증·세션 방어를 외부 보안 인증으로 확대하지 않는다.
- 숨김 미리보기 페이지인 모집 공고·자기소개서 템플릿을 완성 기능으로 소개하지 않는다.
- 서버가 중복 분석 요청을 멱등하게 차단하거나 평가 임계값·면접 질문 개수를 보장한다고 주장하지 않는다.

## 8. 구현 범위

- 실제 프로필 구현 단계에서는 `README.md` 한 파일을 전면 재구성한다.
- 별도 이미지 자산은 추가하지 않는다.
- 현재 UTF-8 인코딩을 유지한다.
- 사용자 저장소의 다른 파일이나 프로젝트 저장소는 수정하지 않는다.
- 브라우저 시각 비교용 임시 파일은 프로필 저장소에 포함하지 않는다.

## 9. 검증 기준

구현 후 다음 항목을 확인한다.

1. `README.md`가 UTF-8로 정상 표시된다.
2. 다섯 프로젝트 링크가 모두 사용자의 개인 저장소를 가리킨다.
3. Hero에서 AI/LLM 풀스택 정체성과 프론트엔드 강점이 동시에 드러난다.
4. HumouR의 팀 성과와 개인 기여가 별도 문단으로 구분된다.
5. 기술 스택은 B안 매트릭스로 표시되고 배지 벽을 중복 사용하지 않는다.
6. 3차 프로젝트의 내부 평가 수치를 포함할 경우 평가 범위와 한계가 함께 적힌다.
7. GitHub Markdown 표와 HTML이 깨지지 않는다.
8. 기존 `codex_subagent`는 `Other Work`에서 유지된다.
9. GitHub 통계는 페이지 하단의 보조 정보로만 남는다.
10. 사실성 가드레일에 위배되는 문장이 없다.
