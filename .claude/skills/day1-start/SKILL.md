---
name: day1-start
description: AX Camp Day 1 시작하기. Claude Code 설치부터 첫 대화, CLAUDE.md 작성, 핵심 기능 이해까지. "1일차", "Day 1", "시작" 요청에 사용.
---

# Day 1: 시작하기

EXEM 임직원을 위한 Claude Code 첫걸음.
코딩 경험이 없어도 됩니다. 이 스킬이 안내합니다.

---

## STOP PROTOCOL — 절대 위반 금지

### 각 블록은 반드시 2턴에 걸쳐 진행한다

┌─ Phase A (첫 번째 턴) ──────────────────────────────┐
│ 1. references/에서 해당 블록 파일의 EXPLAIN 섹션을 읽는다    │
│ 2. 기능을 설명한다                                        │
│ 3. references/에서 해당 블록 파일의 EXECUTE 섹션을 읽는다    │
│ 4. "지금 직접 실행해보세요"라고 안내한다                     │
│ 5. ⛔ 여기서 반드시 STOP. 턴을 종료한다.                    │
│                                                          │
│ ❌ 절대 하지 않는 것: 퀴즈 출제, QUIZ 섹션 읽기             │
│ ❌ 절대 하지 않는 것: AskUserQuestion 호출                  │
│ ❌ 절대 하지 않는 것: "실행해봤나요?" 질문                   │
└──────────────────────────────────────────────────────────┘

  ⬇️ 사용자가 돌아와서 "했어", "완료", "다음" 등을 입력한다

┌─ Phase B (두 번째 턴) ──────────────────────────────┐
│ 1. references/에서 해당 블록 파일의 QUIZ 섹션을 읽는다       │
│ 2. AskUserQuestion으로 퀴즈를 출제한다                     │
│ 3. 정답/오답 피드백을 준다                                 │
│ 4. 다음 블록으로 이동할지 AskUserQuestion으로 묻는다         │
│ 5. ⛔ 다음 블록을 시작하면 다시 Phase A부터.                │
└──────────────────────────────────────────────────────────┘

### 핵심 금지 사항

1. Phase A에서 AskUserQuestion을 호출하지 않는다
2. Phase A에서 퀴즈를 내지 않는다
3. Phase A에서 "실행해봤나요?"를 묻지 않는다
4. 한 턴에 EXPLAIN + QUIZ를 동시에 하지 않는다

### Phase A 종료 시 필수 문구
---
👆 위 내용을 직접 실행해보세요.
실행이 끝나면 "완료" 또는 "다음"이라고 입력해주세요.

---

## 소요 시간 가이드

| Block | 주제 | 예상 시간 |
|-------|------|-----------|
| 0 | Cursor + Claude Code 설치 + 첫 실행 | ~15분 |
| 1 | 첫 대화 + 체험 | ~15분 |
| 2 | CLAUDE.md 나의 규칙서 | ~15분 |
| 3 | 핵심 기능 5분 훑기 | ~15분 |
| 합계 | | ~60분 |

---

## EXEM 맥락

이 캠프는 EXEM 임직원 전용입니다.
- 엔지니어: exemONE, MaxGauge, InterMax 개발/운영에 Claude Code 활용
- 비전공자: BX팀, EX팀 업무 자동화, 문서 작성, 리서치 가속
- 공통: 반복 업무를 Skill로 만들어 팀 전체 생산성 향상

---

## References 파일 맵

| 블록 | 파일 | 내용 |
|------|------|------|
| Block 0 | references/block0-setup.md | Cursor 설치 + Claude Code 설치 + 첫 실행 |
| Block 1 | references/block1-first-chat.md | 첫 대화 + 3가지 체험 |
| Block 2 | references/block2-claude-md.md | CLAUDE.md로 나의 규칙 만들기 |
| Block 3 | references/block3-features.md | 핵심 기능 5분 훑기 (Skill, MCP, Subagent, Hook) |
| 부록 | references/boris-principles.md | Boris Cherny의 Claude Code 워크플로우 원칙 |

---

## 시작

참가자에게 인사하고, Block 0부터 Phase A를 시작한다.
"AX Camp Day 1에 오신 것을 환영합니다!" 로 시작.
