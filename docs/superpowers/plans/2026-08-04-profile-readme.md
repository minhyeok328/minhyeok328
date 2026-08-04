# AI/LLM Full-Stack Profile README Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Replace the existing GitHub profile README with an evidence-based developer introduction that positions Seo Minhyeok as a frontend-strong AI/LLM full-stack developer.

**Architecture:** Keep the profile as one self-contained `README.md` using GitHub-flavored Markdown plus minimal centered HTML for the hero and statistics. Present HumouR as the flagship case study, the five course projects as a verified growth journey, and the selected B-layout technology matrix as the primary stack summary.

**Tech Stack:** GitHub-flavored Markdown, minimal HTML, PowerShell validation, Git.

## Global Constraints

- Implement the approved design in `docs/superpowers/specs/2026-08-04-profile-readme-design.md`.
- Modify only `README.md` during implementation; do not edit the five project repositories.
- Preserve UTF-8 encoding without introducing replacement characters or mojibake.
- Use the five personal repository URLs supplied by the user.
- Separate team-system capabilities from Seo Minhyeok's direct contributions.
- Use the B-layout technology matrix with `Primary` and `Project experience` columns.
- Do not present team-only technologies, internal evaluation results, or deployment configuration as sole personal ownership or production guarantees.
- Keep `codex_subagent` under `Other Work` and GitHub statistics at the bottom.
- Add no new image assets or dependencies.

---

### Task 1: Rebuild and verify the GitHub profile README

**Files:**
- Modify: `README.md`
- Reference: `docs/superpowers/specs/2026-08-04-profile-readme-design.md`
- Reference: `docs/superpowers/plans/2026-08-04-profile-readme.md`

**Interfaces:**
- Consumes: the approved headline, factual guardrails, personal repository URLs, HumouR contribution boundaries, and B-layout stack matrix from the design specification.
- Produces: a UTF-8 GitHub profile `README.md` with the exact top-level sections `About Me`, `Flagship Project`, `Project Journey`, `Tech Stack`, `How I Build`, `Other Work`, and `GitHub Activity`.

- [ ] **Step 1: Run the profile-contract check against the current README and confirm the baseline fails**

Run:

```powershell
$readmeText = [System.IO.File]::ReadAllText((Resolve-Path 'README.md'), [System.Text.Encoding]::UTF8)
$requiredText = @(
  'AI · LLM Full-Stack Developer',
  '## Flagship Project',
  'https://github.com/minhyeok328/Final_project',
  '## Project Journey',
  '| Area | Primary | Project experience |'
)
foreach ($value in $requiredText) {
  if (-not $readmeText.Contains($value)) {
    throw "Missing required profile content: $value"
  }
}
```

Expected: FAIL with `Missing required profile content: AI · LLM Full-Stack Developer`.

- [ ] **Step 2: Replace the Hero, introduction, and navigation**

Keep the existing dark capsule banner and replace the copy below it with this content:

```markdown
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
```

Create `## About Me` with three short paragraphs: LLM features should reach real user workflows; the project history covers data, models, backend, and UI; the strongest direct implementation areas are LangGraph/RAG pipelines and frontend/service integration. State that the recent HumouR role was frontend CODEOWNER for application structure, API contracts, authentication/session boundaries, asynchronous state, QA, and app-level security hardening.

Add a compact `Core Strengths` list with these exact labels and scopes:

```markdown
- **LLM Application:** LangGraph, RAG, structured output, retrieval and generation pipelines
- **Frontend Architecture:** React, TypeScript, TanStack Query, Zod
- **Full-Stack Integration:** Django, FastAPI, REST API, MySQL, SQLite
- **Service Reliability:** authentication, CSRF, error handling, request lifecycle, testing and QA
- **Collaboration:** Git/PR workflow, interface contracts, technical documentation
```

- [ ] **Step 3: Add the HumouR flagship case study with explicit ownership boundaries**

Create `## Flagship Project` and link the title to `https://github.com/minhyeok328/Final_project`.

Describe the team product as an AI-assisted hiring operations platform that connects company information, job descriptions, evaluation checklists, resume analysis, reports, interview questions, restricted sharing, and document chat. State that the repository includes React, Django, Celery, LangGraph, Pinecone, RunPod, and AWS deployment automation, without claiming a currently operating public production service.

Use these personal contribution bullets:

```markdown
- 프론트엔드 CODEOWNER로서 React·TypeScript 애플리케이션의 구조·통합·품질 기준 주도
- Axios·CSRF 요청 계층부터 도메인 API Client, Zod 계약, Adapter, TanStack Query로 이어지는 데이터 흐름 설계
- 일반 계정과 제한 API Key 세션의 권한·캐시 격리
- 인증 만료 처리, 요청 취소, 오류 정제, 캐시 정리 등 요청 수명주기 안정화
- JD·지원서·분석 리포트·외부 공유·문서 챗을 가로지르는 API 연동, 상태 흐름 및 통합 검증
- 프론트엔드 테스트·검증 체계 구축과 확장에 기여. 팀 저장소 기준 테스트 파일 53개와 검증 스크립트 16개
- 코드·API 인터페이스 정의서·운영 문서의 정합성 관리
```

Immediately follow the bullets with a two-row responsibility table:

```markdown
| Boundary | Technologies |
| --- | --- |
| **Direct contribution** | React 19 · TypeScript · Axios · TanStack Query · Zod · Ant Design · Vitest · MSW · Playwright |
| **Team-system integration** | Django API · Celery asynchronous states · LangGraph/Pinecone analysis results · AWS deployment configuration |
```

- [ ] **Step 4: Add the five-project growth journey**

Create `## Project Journey` and use exactly these personal repository URLs:

```text
https://github.com/minhyeok328/1st_project
https://github.com/minhyeok328/2nd_project
https://github.com/minhyeok328/3rd_project
https://github.com/minhyeok328/4th_project
https://github.com/minhyeok328/Final_project
```

Create a four-column table with the stages and verified personal contributions below:

```markdown
| Stage | Project | My Contribution | Growth |
| --- | --- | --- | --- |
| **01 · Data Integration** | 차량 운영·관리 비용 계산 시스템 | 공공 연비 API 수집·JSON 파싱, CSV 로드·파싱, 비용 모델과 데이터 흐름 문서화 | 외부 데이터를 서비스 입력값으로 연결 |
| **02 · ML Experimentation** | 신용카드 고객 이탈 분석 | 전처리 탐색 노트북, Unknown 소득 보완을 위한 XGBoost 그룹 분류 실험, EDA 시각화·Streamlit 프로토타입 | 모델 실험의 한계를 확인하고 사용자에게 전달할 분석으로 확장 |
| **03 · LLM & RAG** | PICKLE 맛집 추천 챗봇 | LangGraph 파이프라인, OpenAI strict JSON Schema 슬롯 추출, SQLite 임베딩 검색 커넥터 연동, Streamlit UI, 3단계 내부 평가 | LLM 응답을 실제 데이터와 근거에 연결 |
| **04 · Web Integration** | LG Home AI 가전 상담 | Django·Tailwind 기반 주요 화면, 검색·필터·찜·채팅 API 연동, 오류·로딩·모바일 UX 개선 | LLM 기능을 계정·대화방 기반 Django 애플리케이션의 사용자 흐름에 통합 |
| **05 · AI Full-Stack** | HumouR | 프론트엔드 CODEOWNER, API 계약·인증·상태·테스트·QA 구조화 | 인증·비동기 상태·오류·검증을 다루는 애플리케이션 구조로 확장 |
```

Turn every project name into its matching repository link. Below the table, state that PICKLE's internally generated 50-case evaluation improved pass rate from 46% to 82% and target inclusion from 52% to 96%; label it as an internal automated evaluation, not production accuracy. Do not include the second project's 90.3% income-group experiment in the profile.

- [ ] **Step 5: Add the selected B-layout technology matrix**

Create `## Tech Stack`, define `Primary` as repeatedly implemented and verified core tools, and define `Project experience` as earlier direct use or interface-boundary integration.

Use this table:

```markdown
| Area | Primary | Project experience |
| --- | --- | --- |
| **Frontend** | React · TypeScript · Axios · TanStack Query · Zod | JavaScript · Tailwind CSS · Ant Design · Django Templates · Streamlit |
| **LLM Application** | LangGraph · LangChain · RAG · OpenAI API · Structured Output | Pinecone integration |
| **Backend & Data** | Python · Django · pandas · scikit-learn · XGBoost | FastAPI consumption · MySQL/SQLite integration · Celery/MLflow boundary |
| **Quality & Delivery** | Vitest · Testing Library · MSW · Playwright · Git/GitHub | Docker · GitHub Actions · AWS deployment configuration understanding |
```

Render technologies as inline code spans in the final README, wrapping long cells with `<br>` only where needed. Do not add a duplicate badge wall below the table.

- [ ] **Step 6: Add working principles, other work, and bottom-weighted activity cards**

Create `## How I Build` with these five principles:

```markdown
- **Connect the whole flow:** 데이터 수집, 모델, API, 상태 관리, UI를 하나의 사용자 흐름으로 연결합니다.
- **Define contracts:** 프론트엔드와 백엔드 사이의 요청·응답 계약을 명확히 정의하고 런타임에서 검증합니다.
- **Design failure states:** 로딩·오류·인증 만료·요청 취소·비동기 처리 상태를 정상 흐름과 함께 설계합니다.
- **Verify repeatedly:** 내부 평가·정적 QA·자동 테스트 등 프로젝트 성격에 맞는 방식으로 반복 검증합니다.
- **Document decisions:** 코드와 인터페이스 문서를 동기화해 팀원이 같은 기준으로 작업할 수 있게 합니다.
```

Create `## Other Work` with a compact link to `https://github.com/minhyeok328/codex_subagent`, describing it as an exploration of Codex subagent orchestration, reusable rules, and documentation verification.

Create `## GitHub Activity` last and retain at most the existing streak and repository-language cards. Do not place activity cards above project or technology content.

- [ ] **Step 7: Run strict content, encoding, link, and formatting validation**

Run:

```powershell
$strictUtf8 = New-Object System.Text.UTF8Encoding($false, $true)
$readmePath = (Resolve-Path 'README.md')
$readmeText = $strictUtf8.GetString([System.IO.File]::ReadAllBytes($readmePath))

$requiredText = @(
  'AI · LLM Full-Stack Developer',
  '## About Me',
  '## Flagship Project',
  '## Project Journey',
  '## Tech Stack',
  '| Area | Primary | Project experience |',
  '## How I Build',
  '## Other Work',
  '## GitHub Activity'
)
foreach ($value in $requiredText) {
  if (-not $readmeText.Contains($value)) { throw "Missing required profile content: $value" }
}

$projectUrls = @(
  'https://github.com/minhyeok328/1st_project',
  'https://github.com/minhyeok328/2nd_project',
  'https://github.com/minhyeok328/3rd_project',
  'https://github.com/minhyeok328/4th_project',
  'https://github.com/minhyeok328/Final_project'
)
foreach ($url in $projectUrls) {
  if ([regex]::Matches($readmeText, [regex]::Escape($url)).Count -lt 1) { throw "Missing project URL: $url" }
}

if ($readmeText.Contains([char]0xFFFD)) { throw 'README contains a Unicode replacement character' }
if ($readmeText -match 'TBD|TODO|FIXME|SKN26-4th-1st|SKN26-3rd-3rd|SKN26-2nd-1st|joy-riders/joy-riders') {
  throw 'README contains a placeholder or obsolete project URL'
}

'Profile README contract passed.'
```

Expected: `Profile README contract passed.`

Run:

```powershell
git diff --check
git diff -- README.md
git status --short
```

Expected: no whitespace errors; the diff contains only the intentional `README.md` rewrite plus the already-created implementation plan if it has not yet been committed.

- [ ] **Step 8: Commit the implementation as a separate logical change**

Inspect the complete README diff, then run:

```powershell
git add -- README.md
git diff --cached --stat
git diff --cached --check
git diff --cached -- README.md
git commit -m "docs(profile): present AI full-stack project journey"
git log -1 --pretty=format:'%H%n%s'
git status --short
```

Expected: one commit containing only `README.md`; the implementation plan remains separately reviewable or committed as its own documentation change.
