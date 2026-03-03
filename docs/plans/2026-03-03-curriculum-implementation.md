# EXEM AI Curriculum Redesign - Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Day 0~5 전체 커리큘럼을 2026년 최신 트렌드 기반으로 재작성. 시각 디자인 시스템 적용, 콘텐츠 전면 교체.

**Architecture:** 기존 `.claude/skills/` 구조 유지. 각 Day 폴더의 SKILL.md + references/*.md를 전면 재작성. 폴더명을 day1/day2/... 로 단순화. CLAUDE.md와 README.md도 업데이트.

**Tech Stack:** Claude Code Skills (SKILL.md + references), Markdown, AskUserQuestion

**Design Doc:** `docs/plans/2026-03-03-curriculum-redesign.md` 참조

---

## Task 1: 폴더 구조 재편 + 기존 파일 정리

**Files:**
- Delete: `.claude/skills/day1-start/` (전체)
- Delete: `.claude/skills/day2-connect/` (전체)
- Delete: `.claude/skills/day3-skill/` (전체)
- Delete: `.claude/skills/day4-apply/` (전체)
- Delete: `.claude/skills/day5-graduate/` (전체)
- Create: `.claude/skills/day1/references/` (빈 디렉토리)
- Create: `.claude/skills/day2/references/` (빈 디렉토리)
- Create: `.claude/skills/day3/references/` (빈 디렉토리)
- Create: `.claude/skills/day4/references/` (빈 디렉토리)
- Create: `.claude/skills/day5/references/` (빈 디렉토리)

**Step 1:** 기존 Day 1~5 폴더 삭제

```bash
cd ~/Desktop/Claude/exem-ai-curriculum-program
rm -rf .claude/skills/day1-start .claude/skills/day2-connect .claude/skills/day3-skill .claude/skills/day4-apply .claude/skills/day5-graduate
```

**Step 2:** 새 폴더 구조 생성

```bash
mkdir -p .claude/skills/day{1,2,3,4,5}/references
```

**Step 3:** Commit

```bash
git add -A && git commit -m "정리(스킬): 기존 Day 1~5 폴더 삭제 + 새 구조 생성"
```

---

## Task 2: Day 0 재작성 — 오리엔테이션

**Files:**
- Modify: `.claude/skills/day0-orientation/SKILL.md`
- Modify: `.claude/skills/day0-orientation/references/orientation.md`

**Step 1:** SKILL.md 재작성

day0-orientation/SKILL.md 내용:
- name: day0-orientation
- description: Day 0 오리엔테이션. 프로젝트를 처음 열었을 때 자동 시작. 5분짜리 안내.
- 진행 방식: 퀴즈 없이 단계별 AskUserQuestion으로 진행
- 순서: EXEM 배너 출력 → 인트로 텍스트 → [1]~[4] 단계 진행
- 설치 미완 시 랜딩 페이지 리디렉션
- 시각 규칙: 디자인 문서의 시각 시스템 전체를 SKILL.md에 명시
- 인용구: Boris Cherny "Claude Code 팀에서는 모두가 코딩합니다."

**Step 2:** references/orientation.md 재작성

4단계 콘텐츠:
- [1] 이건 결국 대화입니다: 웹 Chat vs Claude Code 비교 (아이콘 칼럼). "지금 이 대화 자체가 Claude Code"
- [2] Cursor 안에서 뭘 보고 있는 건지: Cursor 화면 일러스트 (영어 UI, 한글 설명 아래). 파일탐색기/에디터/터미널 3곳
- [3] Claude와 첫 대화: 구체적으로 말할수록 좋다 (😕→🙂→🎯 레벨). "지금 바로 해보세요"
- [4] 멈추기 / 이어하기: 멈출 때 (💬→💾→👋), 이어할 때 (1~4 단계)

각 단계에 프로그레스 바 + 체크리스트 포함.

**Step 3:** Commit

```bash
git add .claude/skills/day0-orientation/ && git commit -m "개선(Day0): 오리엔테이션 전면 재작성 — 시각 디자인 + 인트로 + 설치 리디렉션"
```

---

## Task 3: Day 1 작성 — AI에게 잘 시키는 법

**Files:**
- Create: `.claude/skills/day1/SKILL.md`
- Create: `.claude/skills/day1/references/block1-why-claude-code.md`
- Create: `.claude/skills/day1/references/block2-three-levels.md`
- Create: `.claude/skills/day1/references/block3-claude-md.md`
- Create: `.claude/skills/day1/references/block4-real-work.md`

**Step 1:** SKILL.md 작성

- name: day1
- description: Day 1 AI에게 잘 시키는 법. 컨텍스트 엔지니어링 기초.
- STOP PROTOCOL (Phase A/B) 포함
- 인용구: Tobi Lutke "컨텍스트 엔지니어링"
- 시각 규칙 참조 지시
- Block 1~4 references 파일 맵

**Step 2:** block1-why-claude-code.md 작성

EXPLAIN:
- "왜 굳이 터미널에서?" 질문에 답하는 구조
- 웹 Chat vs Claude Code 비교표 (아이콘 활용)
  - 파일 접근: 복붙 vs 직접
  - 기억: 매번 설명 vs CLAUDE.md
  - 반복: 매번 처음부터 vs /명령어
  - 도구: 브라우저 탭 전환 vs MCP
- Lenny Rachitsky 인용: "Claude Local 또는 Claude Agent로 생각하라"

EXECUTE:
- 체험 과제: 같은 요청을 Claude 웹과 Claude Code에서 해보기
  - "이 프로젝트에 어떤 파일이 있는지 알려줘" → Claude Code는 직접 읽음
  - "README.md를 읽고 3줄로 요약해줘" → Claude Code는 바로 실행

QUIZ:
- "Claude Code가 웹 ChatGPT와 가장 다른 점은?" (파일 직접 접근)

**Step 3:** block2-three-levels.md 작성

EXPLAIN:
- "AI에게 잘 시키는 3가지 레벨"
- Lv.1 구조화된 요청 (CO-STAR 소개):
  - Context, Objective, Style, Tone, Audience, Response
  - EXEM 맥락 예시: 경쟁사 분석 보고서 요청
- Lv.2 AI가 먼저 질문하게 (CRIT Interview):
  - "전략을 제안하기 전에 핵심 질문 5개를 먼저 던져라"
  - 컨설턴트가 첫 미팅에서 질문부터 하는 것과 같은 원리
- Lv.3 시스템에 새기기 (CLAUDE.md 예고):
  - 매번 프롬프트를 잘 쓰는 것보다 시스템을 설계하는 게 더 중요
  - Phil Schmid: "대부분의 에이전트 실패는 모델 실패가 아니라 컨텍스트 실패다"

EXECUTE:
- Lv.1 실습: CO-STAR로 EXEM 마케팅 보고서 요청 작성
- Lv.2 실습: "먼저 질문 5개 해줘" 패턴 체험
- 두 결과 비교

QUIZ:
- "Lv.1과 Lv.2의 핵심 차이는?" (내가 다 지시 vs AI가 역질문)

**Step 4:** block3-claude-md.md 작성

EXPLAIN:
- CLAUDE.md = "내 비서의 업무 매뉴얼"
- Boris Cherny: "실수를 발견하면 CLAUDE.md에 추가. 같은 실수를 반복하지 않게."
- 구성 요소: 이름, 역할, 응답 규칙, EXEM 맥락, 선호 규칙
- 좋은 CLAUDE.md의 원칙: 200줄 이하, 검증 가능한 구체적 지시, 정기 정리

EXECUTE:
- 직접 CLAUDE.md 작성하기:
  1. "나는 [이름]이고 EXEM [팀명]에서 [업무]를 합니다"
  2. 응답 규칙 3가지 추가
  3. 저장 후 Claude에게 "내가 누군지 알아?" 질문 → 기억 확인

QUIZ:
- "CLAUDE.md에 적으면 안 되는 것은?" (비밀번호/API 키 등)

**Step 5:** block4-real-work.md 작성

EXPLAIN:
- Day 1 마무리: 배운 것을 실제 업무에 적용
- CO-STAR + CRIT Interview + CLAUDE.md 조합 활용

EXECUTE:
- 실제 업무 1개 선택 (보고서/요약/정리/리서치)
- CO-STAR 구조로 요청 작성
- Claude Code로 실행
- 결과 평가

QUIZ:
- "오늘 해본 것 중 가장 유용했던 것은?" (정답 없는 체험 확인)

**Step 6:** Commit

```bash
git add .claude/skills/day1/ && git commit -m "기능(Day1): AI에게 잘 시키는 법 — 컨텍스트 엔지니어링 + CO-STAR + CRIT"
```

---

## Task 4: Day 2 작성 — 내 업무를 AI로 해보기

**Files:**
- Create: `.claude/skills/day2/SKILL.md`
- Create: `.claude/skills/day2/references/block1-delegation.md`
- Create: `.claude/skills/day2/references/block2-delegate-practice.md`
- Create: `.claude/skills/day2/references/block3-ai-limits.md`

**Step 1:** SKILL.md 작성

- name: day2
- description: Day 2 내 업무를 AI로 해보기. 위임 프레임워크 + 실무 적용.
- STOP PROTOCOL (Phase A/B) 포함
- 인용구: Ethan Mollick "'좋은 결과'가 어떤 모습인지 알고..."
- Block 1~3 references 파일 맵

**Step 2:** block1-delegation.md 작성

EXPLAIN:
- Ethan Mollick의 위임 프레임워크 소개
- 3분류: Just Me / Delegate / Automate
  - Just Me: 창의적 판단, 대면 소통, 최종 의사결정
  - Delegate: 초안 작성, 데이터 정리, 리서치, 요약
  - Automate: 파일 정리, 형식 변환, 반복 보고서
- "좋은 매니저 = 좋은 AI 사용자" 프레이밍
- Mollick 인용: "소프트 스킬이 결국 하드 스킬이었다"

EXECUTE:
- 내 주간 업무 5~10개를 적고, 3분류로 나누기
- AskUserQuestion으로 분류 결과 공유

QUIZ:
- 업무 분류 예시 문제 (어떤 업무가 Delegate에 적합한가?)

**Step 3:** block2-delegate-practice.md 작성

EXPLAIN:
- Delegate 실습의 3단계: 정의 → 위임 → 검증
  1. "좋은 결과"의 기준을 먼저 정한다
  2. CO-STAR + CRIT로 요청한다
  3. 결과를 내 기준으로 평가하고 피드백한다
- 비유: 신입에게 업무를 맡기는 것과 동일

EXECUTE:
- Block 1에서 Delegate로 분류한 업무 중 1개를 실제로 실행
- 3단계 적용: 기준 정의 → 요청 → 결과 평가 → 피드백 후 재실행
- Before/After 비교

QUIZ:
- "위임 후 결과가 기대에 못 미칠 때 가장 좋은 대응은?" (구체적 피드백 후 재요청)

**Step 4:** block3-ai-limits.md 작성

EXPLAIN:
- AI가 못하는 것:
  - 환각 (확인 안 된 정보를 자신있게 말함)
  - 인터넷 실시간 접근 불가 (MCP 연결 전)
  - 컨텍스트 윈도우 한계
  - 최신 정보 부족 (학습 기준일)
- 대응법: 검증 습관 + 출처 요청 + 단계별 확인

EXECUTE:
- 의도적 실패 체험:
  - "오늘 EXEM 주가 알려줘" → 실패 (인터넷 없음)
  - "최신 exemONE 릴리즈 노트 요약해줘" → 환각 가능성
- 대응 연습: "출처를 밝혀줘", "확실하지 않으면 모른다고 해줘"

QUIZ:
- "Claude가 자신있게 답했지만 틀릴 수 있는 경우는?" (환각)

**Step 5:** Commit

```bash
git add .claude/skills/day2/ && git commit -m "기능(Day2): 내 업무를 AI로 해보기 — 위임 프레임워크 + 실무 적용 + 한계 인식"
```

---

## Task 5: Day 3 작성 — 도구 연결하기 (MCP)

**Files:**
- Create: `.claude/skills/day3/SKILL.md`
- Create: `.claude/skills/day3/references/block1-mcp-concept.md`
- Create: `.claude/skills/day3/references/block2-connect.md`
- Create: `.claude/skills/day3/references/block3-work-with-tools.md`

**Step 1:** SKILL.md 작성

- name: day3
- description: Day 3 도구 연결하기. MCP로 외부 도구 연결.
- STOP PROTOCOL (Phase A/B) 포함
- 인용구: Anthropic "아무리 뛰어난 AI도 데이터에서 고립되면 무력합니다."
- Block 1~3 references 파일 맵
- EXEM 도구 맥락: Mattermost, ClickUp, Notion, GitHub, Google Calendar

**Step 2:** block1-mcp-concept.md 작성

EXPLAIN:
- MCP = AI에게 눈과 손을 달아주는 것
- 일러스트: MCP 아키텍처 (Claude Code ← MCP → 외부 도구들)
  - 영어로 그리고 한글 설명 아래에
- USB-C 비유: 하나의 규격으로 모든 기기 연결
- MCP 없는 AI vs MCP 있는 AI 비교 (아이콘)
  - 없을 때: 브라우저 탭 전환, 복붙, 수동 확인
  - 있을 때: 한 곳에서 모든 도구 접근
- Phil Schmid: "마법은 더 똑똑한 모델이 아니라, 올바른 맥락 제공에 있다"

EXECUTE:
- `/mcp` 명령으로 현재 연결된 MCP 서버 확인
- MCP가 뭔지 Claude에게 직접 물어보기

QUIZ:
- "MCP가 해결하는 핵심 문제는?" (AI와 외부 도구 사이의 연결)

**Step 3:** block2-connect.md 작성

EXPLAIN:
- 실제 MCP 서버 연결 방법: `claude mcp add`
- 권장 서버: Notion 또는 Google Calendar (가장 안정적)
- EXEM 참고: ClickUp MCP는 API 안정성 이슈로 체험 수준만 권장
- 연결 후 확인: `/mcp`로 서버 목록 확인

EXECUTE:
- 단계별 실습:
  1. `claude mcp add` 명령으로 서버 추가
  2. `/mcp`로 연결 확인
  3. 연결된 도구에 간단한 질문 ("내 캘린더에 오늘 일정 뭐 있어?")

QUIZ:
- "MCP 서버를 추가하는 명령어는?" (`claude mcp add`)

**Step 4:** block3-work-with-tools.md 작성

EXPLAIN:
- 연결된 도구로 실제 업무를 해보는 것이 핵심
- 예시 시나리오:
  - Notion: "이번 주 회의록을 요약해줘"
  - Calendar: "다음 주 일정 정리해서 보여줘"
  - 조합: "캘린더에서 이번 주 미팅 목록 가져와서, 각 미팅 준비사항 정리해줘"

EXECUTE:
- 연결한 MCP 도구를 활용한 실제 업무 처리
- 결과를 파일로 저장하는 것까지 체험

QUIZ:
- "MCP 연결 전후로 가장 큰 차이를 느낀 점은?" (정답 없는 체험 확인)

**Step 5:** Commit

```bash
git add .claude/skills/day3/ && git commit -m "기능(Day3): 도구 연결하기 — MCP 개념 + 실습 + 실무 활용"
```

---

## Task 6: Day 4 작성 — 자동화하기 (Skill + 검증 루프)

**Files:**
- Create: `.claude/skills/day4/SKILL.md`
- Create: `.claude/skills/day4/references/block1-what-is-skill.md`
- Create: `.claude/skills/day4/references/block2-build-skill.md`
- Create: `.claude/skills/day4/references/block3-verification.md`

**Step 1:** SKILL.md 작성

- name: day4
- description: Day 4 자동화하기. Skill 제작 + 검증 루프 설계.
- STOP PROTOCOL (Phase A/B) 포함
- 인용구: Boris Cherny "검증 수단을 주면 품질 2~3배"
- Block 1~3 references 파일 맵

**Step 2:** block1-what-is-skill.md 작성

EXPLAIN:
- Skill = 반복 업무를 /명령어로 저장하는 것
- 비유: 요리 레시피. 매번 "양파 썰고 볶고..." 설명 대신 "파스타 레시피대로 해" 한마디
- Skill의 구조: SKILL.md (레시피 제목+설명) + references/ (상세 레시피)
- Boris Cherny: "매일 반복하는 inner loop 워크플로우에 슬래시 명령을 쓴다"
- 예시 시연: 이 커리큘럼 자체가 Skill로 만들어져 있음. `/day4` 를 입력한 것 자체가 Skill 호출

EXECUTE:
- `.claude/skills/` 폴더를 직접 열어서 구조 확인
- "이 프로젝트의 Skill 목록을 알려줘" 실행
- Skill이 어떤 파일들로 구성되는지 탐색

QUIZ:
- "Skill이 웹 ChatGPT에서 프롬프트 저장하는 것과 다른 점은?" (파일 접근 + 자동 로드 + 팀 공유)

**Step 3:** block2-build-skill.md 작성

EXPLAIN:
- 내 Skill 만들기 실습
- SKILL.md 작성법:
  - YAML frontmatter (name, description)
  - 진행 지시 (뭘 하고 어떻게 응답할지)
- references/ 파일 작성법:
  - 구체적 지시 + 예시 + 변수 처리
- EXEM 업무 예시:
  - `/주간보고`: 이번 주 작업 파일 읽어서 보고서 양식으로 정리
  - `/회의록정리`: 회의 내용을 구조화하여 파일로 저장
  - `/경쟁사체크`: 경쟁사 키워드로 관련 정보 수집 요약

EXECUTE:
- 본인 업무 기반 Skill 1개 직접 만들기:
  1. `.claude/skills/내스킬/SKILL.md` 작성
  2. `references/` 에 상세 지시 작성
  3. `/내스킬` 로 실행 테스트

QUIZ:
- 만든 Skill을 실행해보고 "잘 동작했나요?" 확인

**Step 4:** block3-verification.md 작성

EXPLAIN:
- Boris Cherny 핵심 원칙: "검증 루프가 품질을 2~3배 올린다"
- 검증 루프란: AI가 스스로 결과를 확인하는 구조를 Skill에 내장
- 3가지 검증 방법:
  1. 자가 검증: "결과를 다시 읽고 누락된 항목이 있는지 확인해"
  2. 체크리스트: "다음 기준을 모두 충족하는지 확인: [기준1], [기준2]..."
  3. 역검증: "이 보고서를 받는 팀장 입장에서 빠진 정보가 없는지 점검해"
- 비유: 요리사가 맛보기를 하는 것. 레시피에 "맛보고 간 조절" 단계를 넣는 것

EXECUTE:
- Block 2에서 만든 Skill에 검증 단계 추가
- 검증 전/후 결과 비교

QUIZ:
- "검증 루프를 추가했을 때 가장 크게 달라진 점은?" (정답 없는 체험 확인)

**Step 5:** Commit

```bash
git add .claude/skills/day4/ && git commit -m "기능(Day4): 자동화하기 — Skill 제작 + 검증 루프 설계"
```

---

## Task 7: Day 5 작성 — 졸업

**Files:**
- Create: `.claude/skills/day5/SKILL.md`
- Create: `.claude/skills/day5/references/block1-review.md`
- Create: `.claude/skills/day5/references/block2-graduation.md`
- Create: `.claude/skills/day5/references/block3-share.md`

**Step 1:** SKILL.md 작성

- name: day5
- description: Day 5 졸업. 5일간 배운 것을 종합하여 완성.
- STOP PROTOCOL (Phase A/B) 포함
- 인용구: Boris Cherny "'빌더'로 대체될 거예요"
- Block 1~3 references 파일 맵

**Step 2:** block1-review.md 작성

EXPLAIN:
- 5일간 쌓아온 시스템 정리:
  - Day 1: 컨텍스트 엔지니어링 (좋은 질문의 구조)
  - Day 2: 위임의 기술 (AI에게 맡기고 검증)
  - Day 3: MCP (AI에게 도구를 연결)
  - Day 4: Skill + 검증 루프 (반복 가능한 자동화)
- 전체를 관통하는 메시지: "프롬프트를 잘 쓰는 사람 → 컨텍스트를 설계하는 사람 → 빌더"
- 참가자의 현재 CLAUDE.md, 연결한 MCP, 만든 Skill을 돌아보기

EXECUTE:
- "내가 이번 주에 만든 것들을 정리해줘" 실행
- 각 산출물 확인

QUIZ:
- "5일 중 가장 임팩트 있었던 것은?" (정답 없는 회고)

**Step 3:** block2-graduation.md 작성

EXPLAIN:
- 졸업 프로젝트: 본인 업무에 실제로 적용할 워크플로우 1개 완성
- 구성: CLAUDE.md(맥락) + MCP(도구) + Skill(자동화) + 검증 루프
- Day 4에서 만든 Skill을 고도화하거나, 새로운 것을 만들어도 됨
- 30분 제작 시간

EXECUTE:
- 졸업 프로젝트 제작
- 완성 후 실행 테스트

QUIZ:
- "졸업 프로젝트가 완성됐나요?" (완료 확인)

**Step 4:** block3-share.md 작성

EXPLAIN:
- 팀에 공유하는 방법:
  - `.claude/skills/` 폴더를 Git으로 공유
  - 팀원이 같은 프로젝트를 clone하면 모든 Skill을 바로 사용 가능
  - CLAUDE.md에 팀 규칙을 넣으면 팀 전체의 AI 품질이 올라감
- Boris Cherny의 CLAUDE.md 활용법: "팀 CLAUDE.md를 PR 리뷰 때마다 업데이트"
- 마무리 메시지

EXECUTE:
- 졸업 프로젝트 팀 공유 방법 안내
- 커리큘럼 마무리 인사

QUIZ:
- 없음 (마무리)

**Step 5:** Commit

```bash
git add .claude/skills/day5/ && git commit -m "기능(Day5): 졸업 — 5일 정리 + 졸업 프로젝트 + 팀 공유"
```

---

## Task 8: CLAUDE.md + README.md 업데이트

**Files:**
- Modify: `CLAUDE.md`
- Modify: `README.md`

**Step 1:** CLAUDE.md 재작성

핵심 변경:
- 커리큘럼 표 업데이트 (Day 0~5 새 주제, `/day1` `/day2` 등 새 명령어)
- Day 0 자동 시작 지시 유지
- EXEM 업무 환경 정보 유지
- 설치 리디렉션 안내 추가
- 소통 규칙 유지
- EXEM 맥락 유지

**Step 2:** README.md 업데이트

핵심 변경:
- 커리큘럼 표 업데이트
- 설치 안내를 랜딩 페이지 링크로 대체
- 프로그램 소개 텍스트 업데이트

**Step 3:** Commit

```bash
git add CLAUDE.md README.md && git commit -m "개선(전체): CLAUDE.md + README 커리큘럼 구조 업데이트"
```

---

## 실행 순서

Task 1 (폴더 정리) → Task 2~7 (Day 0~5, 병렬 가능) → Task 8 (CLAUDE.md + README)

Task 2~7은 서로 독립적이므로 병렬 실행 가능.
