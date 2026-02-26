---
name: day2-connect
description: AX Camp Day 2 외부 도구 연결. MCP로 Mattermost/Notion/ClickUp 등을 Claude에 연결하고, Context Sync 스킬의 뼈대를 만든다. "2일차", "Day 2", "MCP", "연결" 요청에 사용.
---

# Day 2: 외부 도구 연결

Claude Code에 Mattermost, Notion, ClickUp 등을 연결합니다.
연결한 도구들로 업무 컨텍스트를 자동 수집하는 스킬의 뼈대를 만듭니다.

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
└──────────────────────────────────────────────────────────┘

  ⬇️ 사용자가 "완료", "다음" 등을 입력한다

┌─ Phase B (두 번째 턴) ──────────────────────────────┐
│ 1. references/에서 해당 블록 파일의 QUIZ 섹션을 읽는다       │
│ 2. AskUserQuestion으로 퀴즈를 출제한다                     │
│ 3. 정답/오답 피드백 후 다음 블록으로                        │
└──────────────────────────────────────────────────────────┘

### Phase A 종료 시 필수 문구
---
👆 위 내용을 직접 실행해보세요.
실행이 끝나면 "완료" 또는 "다음"이라고 입력해주세요.

---

## 소요 시간 가이드

| Block | 주제 | 예상 시간 |
|-------|------|-----------|
| 0 | MCP 개념 이해 | ~10분 |
| 1 | MCP 서버 연결 | ~20분 |
| 2 | Context Sync 뼈대 만들기 | ~30분 |
| 합계 | | ~60분 |

---

## References 파일 맵

| 블록 | 파일 | 내용 |
|------|------|------|
| Block 0 | references/block0-mcp-concept.md | MCP가 뭔지, USB-C 비유, 아키텍처 |
| Block 1 | references/block1-add-server.md | claude mcp add로 실제 서버 연결 + /mcp 탐색 |
| Block 2 | references/block2-context-sync.md | Context Sync 스킬 뼈대 만들기 |

---

## 시작

"Day 2: 외부 도구 연결에 오신 것을 환영합니다!" 로 시작.
Block 0부터 Phase A를 시작한다.
