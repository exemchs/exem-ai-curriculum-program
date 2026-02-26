# Block 0: Subagent로 병렬 수집

## EXPLAIN

> 📖 공식 문서: https://code.claude.com/docs/ko/sub-agents

### Subagent란?

Claude가 혼자서 모든 걸 하는 대신, **여러 AI를 동시에 보내서 작업**하는 것입니다.

비유: 팀장이 3명의 팀원에게 각각 다른 자료를 조사하라고 시킨 뒤, 결과를 모아서 보고서를 만드는 것.

```
Claude (리더)
  │
  ├── Subagent 1 → Mattermost 메시지 수집   ─┐
  ├── Subagent 2 → Notion 문서 수집         ─┼── 동시 실행
  └── Subagent 3 → Calendar 일정 수집       ─┘
  │
  ▼
Claude (리더): 3가지 결과를 종합하여 문서 완성
```

### 왜 필요한가?

| 순차 실행 | 병렬 실행 (Subagent) |
|----------|-------------------|
| Mattermost 수집 → 기다림 → Notion 수집 → 기다림 | 3개 동시 수집 |
| 3분 | 1분 |

### 스킬에 Subagent 넣는 법

SKILL.md에 이렇게 작성합니다:

```markdown
## 실행 흐름

다음 작업을 **Subagent를 사용하여 병렬로** 실행한다:

1. **Mattermost 수집** (subagent): #general 채널의 이번 주 메시지 요약
2. **Notion 수집** (subagent): "주간회의" 페이지 최신 내용
3. **Calendar 수집** (subagent): 이번 주 일정 목록

모든 Subagent 결과를 종합하여 주간 현황 문서를 생성한다.
```

Claude는 이 지시를 읽고 자동으로 Subagent를 만들어 병렬 실행합니다.

## EXECUTE

Day 2에서 만든 스킬의 SKILL.md를 열어서, 병렬 수집 패턴을 적용하세요:

```
Day 2에서 만든 내 스킬의 SKILL.md를 읽어줘.
수집 항목들을 Subagent로 병렬 실행하도록 수정해줘.
```

> SKILL.md를 직접 읽고 수정 제안을 받는 것이 핵심입니다.

## QUIZ

```json
AskUserQuestion({
  "questions": [{
    "question": "Subagent의 장점은?",
    "header": "Quiz: Subagent",
    "options": [
      {"label": "여러 작업을 동시에 실행해서 빠름", "description": "병렬 실행이 핵심"},
      {"label": "AI가 더 똑똑해짐", "description": "똑똑함이 아니라 속도입니다"},
      {"label": "코드를 자동으로 작성함", "description": "그건 Claude Code의 기본 기능입니다"}
    ],
    "multiSelect": false
  }]
})
```

정답: 1번. Subagent는 **여러 작업을 동시에 실행**해서 시간을 절약합니다.
