<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rounded&color=0D1117&height=135&section=header&text=Hi%2C%20I'm%20Minhyeok&fontColor=ffffff&fontSize=32&fontFamily=Varela%20Round" alt="Hi, I'm Minhyeok" />
</p>

<h1 align="center">AI · LLM Full-Stack Developer</h1>

<p align="center">
  <strong>프론트엔드 강점을 기반으로 LLM, API, 데이터 흐름을 연결해 사용자에게 닿는 AI 서비스를 만듭니다.</strong><br>
  데이터·모델·백엔드·사용자 화면으로 이어지는 전체 흐름을 경험하고 연결합니다.
</p>

<p align="center">
  <a href="#about-me">About Me</a> ·
  <a href="#flagship-project">Flagship Project</a> ·
  <a href="#project-journey">Project Journey</a> ·
  <a href="#tech-stack">Tech Stack</a> ·
  <a href="#how-i-build">How I Build</a>
</p>

---

## About Me

LLM 기능이 모델 데모에 머무르지 않고 실제 사용자의 업무 흐름에 닿도록 구현합니다.

데이터 수집·전처리, 모델 실험, 백엔드 API, 사용자 UI까지 이어지는 프로젝트 경험을 쌓았습니다.

특히 LangGraph·RAG 파이프라인과 프론트엔드·서비스 통합을 직접 구현해 왔습니다. 최근 HumouR에서는 프론트엔드 CODEOWNER로서 애플리케이션 구조, API 계약, 인증·세션 경계, 비동기 상태, QA와 애플리케이션 수준의 보안 강화를 담당했습니다.

### Core Strengths

- **LLM Application:** LangGraph, RAG, structured output, retrieval and generation pipelines
- **Frontend Architecture:** React, TypeScript, TanStack Query, Zod
- **Full-Stack Integration:** Django, FastAPI, REST API, MySQL, SQLite
- **Service Reliability:** authentication, CSRF, error handling, request lifecycle, testing and QA
- **Collaboration:** Git/PR workflow, interface contracts, technical documentation

## Flagship Project

### [HumouR](https://github.com/minhyeok328/Final_project)

HumouR는 기업 정보, 채용 공고, 평가 체크리스트, 지원서 분석, 리포트, 면접 질문, 제한 공유와 문서 챗을 하나의 흐름으로 연결한 AI 기반 채용 운영 팀 프로젝트입니다. 저장소에는 React, Django, Celery, LangGraph, Pinecone, RunPod와 AWS 배포 자동화 구성이 포함되어 있으며, 현재 공개 운영 중인 프로덕션 서비스로 소개하는 것은 아닙니다.

- 프론트엔드 CODEOWNER로서 React·TypeScript 애플리케이션의 구조·통합·품질 기준 주도
- Axios·CSRF 요청 계층부터 도메인 API Client, Zod 계약, Adapter, TanStack Query로 이어지는 데이터 흐름 설계
- 일반 계정과 제한 API Key 세션의 권한·캐시 격리
- 인증 만료 처리, 요청 취소, 오류 정제, 캐시 정리 등 요청 수명주기 안정화
- JD·지원서·분석 리포트·외부 공유·문서 챗을 가로지르는 API 연동, 상태 흐름 및 통합 검증
- 프론트엔드 테스트·검증 체계 구축과 확장에 기여. 팀 저장소 기준 테스트 파일 53개와 검증 스크립트 16개
- 코드·API 인터페이스 정의서·운영 문서의 정합성 관리

| Boundary | Technologies |
| --- | --- |
| **Direct contribution** | React 19 · TypeScript · Axios · TanStack Query · Zod · Ant Design · Vitest · MSW · Playwright |
| **Team-system integration** | Django API · Celery asynchronous states · LangGraph/Pinecone analysis results · AWS deployment configuration |

## Project Journey

> 아래 5개 프로젝트는 모두 팀 프로젝트이며, `My Contribution`에는 제가 직접 맡은 범위만 적었습니다.

| Stage | Project | My Contribution | Growth |
| --- | --- | --- | --- |
| **01 · Data Integration** | [차량 운영·관리 비용 계산 시스템](https://github.com/minhyeok328/1st_project) | 공공 연비 API 수집·JSON 파싱, CSV 로드·파싱, 비용 모델과 데이터 흐름 문서화 | 외부 데이터를 서비스 입력값으로 연결 |
| **02 · ML Experimentation** | [신용카드 고객 이탈 분석](https://github.com/minhyeok328/2nd_project) | 전처리 탐색 노트북, Unknown 소득 보완을 위한 XGBoost 그룹 분류 실험, EDA 시각화·Streamlit 프로토타입 | 모델 실험의 한계를 확인하고 사용자에게 전달할 분석으로 확장 |
| **03 · LLM & RAG** | [PICKLE 맛집 추천 챗봇](https://github.com/minhyeok328/3rd_project) | LangGraph 파이프라인, OpenAI strict JSON Schema 슬롯 추출, SQLite 임베딩 검색 커넥터 연동, Streamlit UI, 3단계 내부 평가 | LLM 응답을 실제 데이터와 근거에 연결 |
| **04 · Web Integration** | [LG Home AI 가전 상담](https://github.com/minhyeok328/4th_project) | Django·Tailwind 기반 주요 화면, 검색·필터·찜·채팅 API 연동, 오류·로딩·모바일 UX 개선 | LLM 기능을 계정·대화방 기반 Django 애플리케이션의 사용자 흐름에 통합 |
| **05 · AI Full-Stack** | [HumouR](https://github.com/minhyeok328/Final_project) | 프론트엔드 CODEOWNER, API 계약·인증·상태·테스트·QA 구조화 | 인증·비동기 상태·오류·검증을 다루는 애플리케이션 구조로 확장 |

내부에서 생성한 50개 케이스 자동 평가에서 통과율이 46%에서 82%로, 타깃 포함률이 52%에서 96%로 개선되었습니다. 이는 프로덕션 정확도가 아닌 내부 자동 평가 결과입니다.

## Tech Stack

`Primary`는 반복적으로 직접 구현하고 검증한 핵심 기술이며, `Project experience`는 이전 프로젝트에서 직접 사용했거나 인터페이스 경계에서 연동한 기술입니다.

| Area | Primary | Project experience |
| --- | --- | --- |
| **Frontend** | `React` · `TypeScript` · `Axios` · `TanStack Query` · `Zod` | `JavaScript` · `Tailwind CSS` · `Ant Design` · `Django Templates` · `Streamlit` |
| **LLM Application** | `LangGraph` · `LangChain` · `RAG` · `OpenAI API` · `Structured Output` | `Pinecone integration` |
| **Backend & Data** | `Python` · `Django` · `pandas` · `scikit-learn` · `XGBoost` | `FastAPI consumption` · `MySQL/SQLite integration`<br>`Celery/MLflow boundary` |
| **Quality & Delivery** | `Vitest` · `Testing Library` · `MSW` · `Playwright` · `Git/GitHub` | `Docker` · `GitHub Actions` · `AWS deployment configuration understanding` |

## How I Build

- **Connect the whole flow:** 데이터 수집, 모델, API, 상태 관리, UI를 하나의 사용자 흐름으로 연결합니다.
- **Define contracts:** 프론트엔드와 백엔드 사이의 요청·응답 계약을 명확히 정의하고 런타임에서 검증합니다.
- **Design failure states:** 로딩·오류·인증 만료·요청 취소·비동기 처리 상태를 정상 흐름과 함께 설계합니다.
- **Verify repeatedly:** 내부 평가·정적 QA·자동 테스트 등 프로젝트 성격에 맞는 방식으로 반복 검증합니다.
- **Document decisions:** 코드와 인터페이스 문서를 동기화해 팀원이 같은 기준으로 작업할 수 있게 합니다.

## Other Work

- [codex_subagent](https://github.com/minhyeok328/codex_subagent): an exploration of Codex subagent orchestration, reusable rules, and documentation verification.

## GitHub Activity

<p align="center">
  <img height="195" src="https://streak-stats.demolab.com?user=minhyeok328&theme=github-dark-blue" alt="GitHub Streak" />
  <img height="195" src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=minhyeok328&theme=github_dark" alt="Top Languages by Repo" />
</p>
