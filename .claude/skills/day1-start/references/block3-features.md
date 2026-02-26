# Block 3: 핵심 기능 5분 훑기

## EXPLAIN

> 📖 공식 문서: https://code.claude.com/docs/ko/features-overview

> 외울 필요 없습니다. "이런 게 있구나"만 알면 됩니다.
> 각 기능은 Day 2~5에서 하나씩 자세히 배웁니다.

### Claude Code 핵심 기능 4가지

```
┌─────────────────────────────────────────────────┐
│                  Claude Code                     │
│                                                  │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐       │
│  │  Skill   │  │   MCP    │  │ Subagent │       │
│  │ 나만의    │  │ 외부 도구 │  │ AI 팀    │       │
│  │ 자동화    │  │ 연결     │  │ 협업     │       │
│  └──────────┘  └──────────┘  └──────────┘       │
│                                                  │
│  ┌──────────┐                                    │
│  │  Hook    │                                    │
│  │ 자동 실행 │                                    │
│  └──────────┘                                    │
└─────────────────────────────────────────────────┘
```

| 기능 | 한 줄 설명 | EXEM 예시 |
|------|-----------|-----------|
| **Skill** | `/명령어`로 실행하는 나만의 자동화 | `/weekly-report` → 주간보고 자동 생성 |
| **MCP** | 외부 도구를 Claude에 연결하는 규격 | Mattermost, Notion 등을 Claude가 직접 사용 |
| **Subagent** | 여러 AI가 동시에 작업하는 팀워크 | 3개 DB를 동시에 분석 → 결과 종합 |
| **Hook** | 특정 시점에 자동으로 실행되는 스크립트 | 코드 저장 시 자동으로 테스트 실행 |

### Skill — 가장 중요

Skill은 이 캠프의 핵심입니다. 지금 배우고 있는 이 수업도 Skill입니다.

```
/day1-start  ← 이것도 Skill
/weekly-sync ← 주간 동기화 Skill
/my-skill    ← 내가 만든 Skill
```

Day 3에서 직접 자신만의 Skill을 만듭니다.

### MCP — USB-C 비유

USB-C가 충전기, 모니터, 외장하드를 모두 연결하듯, MCP는 Mattermost, Notion, DB를 모두 Claude에 연결합니다.

```
Claude ←── MCP ──→ Mattermost
                ──→ Notion
                ──→ ClickUp
                ──→ DB
```

Day 2에서 직접 MCP 서버를 연결합니다.

### Subagent — AI 팀

혼자서 모든 걸 하는 대신, 여러 AI를 동시에 보내서 병렬로 작업합니다.

```
나: "3개 팀의 이번 주 현황을 정리해줘"

Claude(리더)
  ├── Subagent 1 → BX팀 Mattermost 수집
  ├── Subagent 2 → EX팀 Mattermost 수집
  └── Subagent 3 → 개발팀 Mattermost 수집

Claude(리더): 3팀 현황 종합 보고서 완성
```

### Hook — 자동 실행

특정 이벤트가 발생하면 자동으로 실행됩니다. 고급 기능이라 이 캠프에서는 개념만 이해하면 됩니다.

## EXECUTE

아래 질문들을 Claude에게 직접 던져보세요:

1. `Skill이 뭐야? EXEM에서 어떤 Skill을 만들 수 있을지 3가지 예시 들어줘`
2. `MCP가 뭐야? EXEM에서 연결하면 좋을 외부 도구 3가지 추천해줘`
3. `Subagent가 뭐야? 내 업무에서 병렬로 처리하면 좋을 작업이 있을까?`

> 답을 외울 필요 없습니다. "이런 게 있구나"를 체험하는 것이 목표입니다.

## QUIZ

```json
AskUserQuestion({
  "questions": [{
    "question": "Skill을 한 마디로 설명하면?",
    "header": "Quiz: 핵심 기능",
    "options": [
      {"label": "나만의 자동화 명령어", "description": "/명령어로 실행하는 자동화"},
      {"label": "외부 도구 연결", "description": "그건 MCP입니다"},
      {"label": "AI 팀워크", "description": "그건 Subagent입니다"},
      {"label": "자동 실행 스크립트", "description": "그건 Hook입니다"}
    ],
    "multiSelect": false
  }]
})
```

정답: 1번. Skill은 `/명령어`로 실행하는 **나만의 자동화**입니다.

```json
AskUserQuestion({
  "questions": [{
    "question": "Day 1을 마치셨습니다! 내일 Day 2에서는 외부 도구를 Claude에 연결하는 MCP를 배웁니다. 오늘 수고하셨습니다!",
    "header": "Day 1 완료 🎉",
    "options": [
      {"label": "수고했어요!", "description": "Day 2에서 만나요"}
    ],
    "multiSelect": false
  }]
})
```
