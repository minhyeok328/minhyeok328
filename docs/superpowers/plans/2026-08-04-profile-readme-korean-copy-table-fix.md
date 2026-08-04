# Profile README Korean Copy and Table Fix Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** 핵심 설명 문장을 한국어로 통일하고 깨진 `Project Journey` 4열 표를 GitHub Flavored Markdown 표로 복구한다.

**Architecture:** 추적 파일 변경은 `README.md` 한 파일로 제한한다. 영문 섹션명·표 헤더·기술명은 유지하고 승인된 네 영역의 설명 문장만 한국어로 교체하며, 표 렌더링 문제는 4개 헤더 열과 4개 구분선 열을 일치시키는 최소 수정으로 해결한다.

**Tech Stack:** GitHub Flavored Markdown · UTF-8 · PowerShell content contract · Git

## Global Constraints

- 기준 설계는 `docs/superpowers/specs/2026-08-04-profile-readme-design.md`이다.
- 영문 섹션명, 표 헤더와 기술명은 유지하고 설명형 본문은 한국어로 작성한다.
- 문구 보정 범위는 `About Me` 3개 문단, HumouR 서비스 소개, PICKLE 내부 평가 설명과 Tech Stack 분류 설명이다.
- `Core Strengths`, `Boundary`, `Technologies`, `Stage`, `Project`, `My Contribution`, `Growth`, `Area`, `Primary`, `Project experience` 표기는 그대로 유지한다.
- `Project Journey` 헤더와 구분선은 모두 4열이어야 하며 구분선은 정확히 `| --- | --- | --- | --- |`이다.
- 다섯 프로젝트는 팀 프로젝트이고 `My Contribution`에는 직접 기여만 적는다는 고지를 유지한다.
- PICKLE 수치는 내부 자동 평가로 표시하고 프로덕션 정확도로 표현하지 않는다.
- HumouR는 현재 공개 운영 중인 프로덕션 서비스로 표현하지 않는다.
- 다섯 개인 저장소 URL, 기술 매트릭스, `codex_subagent`, GitHub Activity 카드와 기존 섹션 순서를 변경하지 않는다.
- `README.md`는 엄격한 UTF-8로 디코딩되어야 하고 Unicode replacement character를 포함하지 않아야 한다.
- 이미지, 의존성, 테스트 파일을 추가하지 않는다.

---

### Task 1: Localize narrative copy and restore the Project Journey table

**Files:**
- Modify: `README.md:24-73`
- Reference: `docs/superpowers/specs/2026-08-04-profile-readme-design.md:68-156`
- Test: inline PowerShell README contract; no tracked test file

**Interfaces:**
- Consumes: 현재 README의 섹션 구조, 프로젝트 URL, 기여 경계, 기술 매트릭스와 승인된 한국어 문구.
- Produces: 엄격한 UTF-8 README, 한국어 핵심 설명 6개, 4열로 렌더링 가능한 `Project Journey` 표.

- [ ] **Step 1: Run the failing Korean-copy and table-structure contract**

Run:

```powershell
$ErrorActionPreference = 'Stop'
$strictUtf8 = New-Object System.Text.UTF8Encoding($false, $true)
$readmePath = Resolve-Path 'README.md'
$readmeText = $strictUtf8.GetString([System.IO.File]::ReadAllBytes($readmePath))
$lines = [System.IO.File]::ReadAllLines($readmePath, $strictUtf8)

$journeyHeader = '| Stage | Project | My Contribution | Growth |'
$headerIndex = [Array]::IndexOf($lines, $journeyHeader)
if ($headerIndex -lt 0) { throw 'Project Journey header is missing' }
$separator = $lines[$headerIndex + 1]
$headerColumns = ($journeyHeader.Trim('|').Split('|')).Count
$separatorColumns = ($separator.Trim('|').Split('|')).Count
if ($headerColumns -ne $separatorColumns) {
  throw "Project Journey table mismatch: header=$headerColumns separator=$separatorColumns"
}

$requiredKorean = @(
  'LLM 기능이 모델 데모에 머무르지 않고 실제 사용자의 업무 흐름에 닿도록 구현합니다.',
  '데이터 수집·전처리, 모델 실험, 백엔드 API, 사용자 UI까지 이어지는 프로젝트 경험을 쌓았습니다.',
  '특히 LangGraph·RAG 파이프라인과 프론트엔드·서비스 통합을 직접 구현해 왔습니다.',
  'HumouR는 기업 정보, 채용 공고, 평가 체크리스트, 지원서 분석, 리포트, 면접 질문, 제한 공유와 문서 챗을 하나의 흐름으로 연결한 AI 기반 채용 운영 팀 프로젝트입니다.',
  '내부에서 생성한 50개 케이스 자동 평가에서 통과율이 46%에서 82%로, 타깃 포함률이 52%에서 96%로 개선되었습니다.',
  '`Primary`는 반복적으로 직접 구현하고 검증한 핵심 기술이며, `Project experience`는 이전 프로젝트에서 직접 사용했거나 인터페이스 경계에서 연동한 기술입니다.'
)
foreach ($value in $requiredKorean) {
  if (-not $readmeText.Contains($value)) { throw "Missing Korean narrative: $value" }
}
```

Expected: FAIL first with `Project Journey table mismatch: header=4 separator=3`.

- [ ] **Step 2: Replace the About Me paragraphs with the approved Korean copy**

Replace only the three English paragraphs under `## About Me` with:

```markdown
LLM 기능이 모델 데모에 머무르지 않고 실제 사용자의 업무 흐름에 닿도록 구현합니다.

데이터 수집·전처리, 모델 실험, 백엔드 API, 사용자 UI까지 이어지는 프로젝트 경험을 쌓았습니다.

특히 LangGraph·RAG 파이프라인과 프론트엔드·서비스 통합을 직접 구현해 왔습니다. 최근 HumouR에서는 프론트엔드 CODEOWNER로서 애플리케이션 구조, API 계약, 인증·세션 경계, 비동기 상태, QA와 애플리케이션 수준의 보안 강화를 담당했습니다.
```

Do not change `### Core Strengths` or its list.

- [ ] **Step 3: Replace the HumouR introduction with the approved Korean copy**

Replace only the English paragraph directly under the HumouR repository link with:

```markdown
HumouR는 기업 정보, 채용 공고, 평가 체크리스트, 지원서 분석, 리포트, 면접 질문, 제한 공유와 문서 챗을 하나의 흐름으로 연결한 AI 기반 채용 운영 팀 프로젝트입니다. 저장소에는 React, Django, Celery, LangGraph, Pinecone, RunPod와 AWS 배포 자동화 구성이 포함되어 있으며, 현재 공개 운영 중인 프로덕션 서비스로 소개하는 것은 아닙니다.
```

Keep the personal-contribution bullets and the direct/team-system boundary table unchanged.

- [ ] **Step 4: Repair the Project Journey delimiter row**

Replace:

```markdown
| --- | --- | --- |
```

with:

```markdown
| --- | --- | --- | --- |
```

Only the delimiter immediately after `| Stage | Project | My Contribution | Growth |` may change. Keep the blank line before the table and all five project rows.

- [ ] **Step 5: Translate the PICKLE evaluation and Tech Stack definition**

Replace the English PICKLE sentence below the journey table with:

```markdown
내부에서 생성한 50개 케이스 자동 평가에서 통과율이 46%에서 82%로, 타깃 포함률이 52%에서 96%로 개선되었습니다. 이는 프로덕션 정확도가 아닌 내부 자동 평가 결과입니다.
```

Replace the English definition below `## Tech Stack` with:

```markdown
`Primary`는 반복적으로 직접 구현하고 검증한 핵심 기술이며, `Project experience`는 이전 프로젝트에서 직접 사용했거나 인터페이스 경계에서 연동한 기술입니다.
```

Keep the technology matrix unchanged.

- [ ] **Step 6: Run the full UTF-8, copy, table, URL, and scope contract**

Run:

```powershell
$ErrorActionPreference = 'Stop'
$strictUtf8 = New-Object System.Text.UTF8Encoding($false, $true)
$readmePath = Resolve-Path 'README.md'
$readmeBytes = [System.IO.File]::ReadAllBytes($readmePath)
$readmeText = $strictUtf8.GetString($readmeBytes)
$lines = [System.IO.File]::ReadAllLines($readmePath, $strictUtf8)

$requiredKorean = @(
  'LLM 기능이 모델 데모에 머무르지 않고 실제 사용자의 업무 흐름에 닿도록 구현합니다.',
  '데이터 수집·전처리, 모델 실험, 백엔드 API, 사용자 UI까지 이어지는 프로젝트 경험을 쌓았습니다.',
  '특히 LangGraph·RAG 파이프라인과 프론트엔드·서비스 통합을 직접 구현해 왔습니다.',
  'HumouR는 기업 정보, 채용 공고, 평가 체크리스트, 지원서 분석, 리포트, 면접 질문, 제한 공유와 문서 챗을 하나의 흐름으로 연결한 AI 기반 채용 운영 팀 프로젝트입니다.',
  '내부에서 생성한 50개 케이스 자동 평가에서 통과율이 46%에서 82%로, 타깃 포함률이 52%에서 96%로 개선되었습니다.',
  '이는 프로덕션 정확도가 아닌 내부 자동 평가 결과입니다.',
  '`Primary`는 반복적으로 직접 구현하고 검증한 핵심 기술이며, `Project experience`는 이전 프로젝트에서 직접 사용했거나 인터페이스 경계에서 연동한 기술입니다.'
)
foreach ($value in $requiredKorean) {
  if (-not $readmeText.Contains($value)) { throw "Missing Korean narrative: $value" }
}

$forbiddenEnglish = @(
  'I build LLM features that reach real user workflows rather than stopping at a model demonstration.',
  'My project history spans data collection and preparation, model experimentation, backend APIs, and user-facing UI.',
  'My strongest direct implementation areas are LangGraph/RAG pipelines and frontend-to-service integration.',
  'HumouR is a team-built AI-assisted hiring operations platform',
  "PICKLE's internally generated 50-case evaluation",
  '`Primary` means repeatedly implemented and verified core tools.'
)
foreach ($value in $forbiddenEnglish) {
  if ($readmeText.Contains($value)) { throw "English narrative remains: $value" }
}

$tableHeaders = @(
  '| Boundary | Technologies |',
  '| Stage | Project | My Contribution | Growth |',
  '| Area | Primary | Project experience |'
)
foreach ($header in $tableHeaders) {
  $index = [Array]::IndexOf($lines, $header)
  if ($index -lt 0) { throw "Missing table header: $header" }
  if ($index -eq 0 -or $lines[$index - 1] -ne '') { throw "Table needs a blank line before header: $header" }
  $separator = $lines[$index + 1]
  $headerColumns = ($header.Trim('|').Split('|')).Count
  $separatorCells = $separator.Trim('|').Split('|')
  $separatorColumns = $separatorCells.Count
  if ($headerColumns -ne $separatorColumns) {
    throw "Table mismatch: $headerColumns header columns, $separatorColumns separator columns for $header"
  }
  foreach ($cell in $separatorCells) {
    if ($cell.Trim() -notmatch '^:?-{3,}:?$') { throw "Invalid table delimiter cell '$cell' for $header" }
  }
}

$projectUrls = @(
  'https://github.com/minhyeok328/1st_project',
  'https://github.com/minhyeok328/2nd_project',
  'https://github.com/minhyeok328/3rd_project',
  'https://github.com/minhyeok328/4th_project',
  'https://github.com/minhyeok328/Final_project'
)
foreach ($url in $projectUrls) {
  if (-not $readmeText.Contains($url)) { throw "Missing project URL: $url" }
}

if ($readmeText.Contains([char]0xFFFD)) { throw 'README contains a Unicode replacement character' }
if (-not $readmeText.Contains('모두 팀 프로젝트')) { throw 'Team-project ownership disclosure is missing' }
if ($readmeText -match '90\.3%|0\.968|TBD|TODO|FIXME') { throw 'README contains a forbidden metric or placeholder' }

'README Korean copy and table contract passed.'
```

Expected: `README Korean copy and table contract passed.`

- [ ] **Step 7: Inspect the exact diff and whitespace state**

Run:

```powershell
git diff --check
git diff -- README.md
git status --short
```

Expected: no whitespace errors; only `README.md` is modified; the diff contains the four approved narrative areas and one added table delimiter cell.

- [ ] **Step 8: Commit the README fix as one logical documentation change**

Run:

```powershell
git add -- README.md
git diff --cached --stat
git diff --cached --check
git diff --cached -- README.md
git commit -m "docs(profile): localize narrative and repair journey table"
git log -1 --pretty=format:'%H%n%s'
git status --short
```

Expected: one commit containing only `README.md`; final working tree is clean.
