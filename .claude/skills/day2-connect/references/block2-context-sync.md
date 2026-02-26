# Block 2: Context Sync 스킬 뼈대 만들기

## EXPLAIN

> Day 2의 목표: 여러 도구에서 정보를 자동으로 수집하는 **나만의 스킬**의 뼈대를 만듭니다.

### Context Sync란?

Mattermost, Notion, Calendar 등 여러 도구에 흩어진 정보를 한번에 수집해서 하나의 문서로 만드는 것입니다.

```
/my-sync 실행
  │
  ├── Mattermost → 이번 주 중요 메시지 수집
  ├── Notion → 진행 중인 프로젝트 현황
  └── Calendar → 이번 주 일정
  │
  ▼
📄 이번 주 업무 현황 문서 자동 생성
```

### 스킬 파일 구조

```
.claude/skills/my-sync/
├── SKILL.md        ← 스킬의 본체 (Claude가 읽는 지시문)
└── references/     ← 참고 자료 (필요할 때 읽음)
```

**SKILL.md** 하나만 있으면 스킬이 됩니다. `/my-sync`로 실행할 수 있습니다.

### SKILL.md 최소 구조

```markdown
---
name: my-sync
description: 업무 컨텍스트를 자동 수집하는 스킬
---

# My Sync

## 실행 흐름
1. Mattermost에서 이번 주 메시지 수집
2. 주요 내용 요약
3. 문서로 정리

## 출력 형식
- 날짜
- 주요 이슈
- 할 일
```

### EXEM 예시

EXEM에서 만들 수 있는 Context Sync 스킬:

| 스킬 이름 | 수집 대상 | 결과 |
|-----------|----------|------|
| `/weekly-report` | Mattermost + Notion | 주간 보고서 자동 생성 |
| `/meeting-prep` | Calendar + Notion | 회의 준비 자료 정리 |
| `/project-status` | GitHub + ClickUp | 프로젝트 진행 현황 |

## EXECUTE

직접 스킬 뼈대를 만들어보세요. Claude에게 이렇게 요청하세요:

```
나만의 Context Sync 스킬을 만들고 싶어.
.claude/skills/ 디렉토리에 만들어줘.

내가 수집하고 싶은 정보:
- [여기에 자신이 수집하고 싶은 정보를 적으세요]
  예: "매주 월요일 팀 Mattermost 채널의 주요 메시지"
  예: "진행 중인 ClickUp 태스크 현황"
  예: "이번 주 회의 일정"

스킬 이름은 [원하는 이름]으로 해줘.
```

> 완벽하지 않아도 됩니다. 뼈대만 만들고, Day 3에서 발전시킵니다.

## QUIZ

```json
AskUserQuestion({
  "questions": [{
    "question": "스킬을 만들려면 최소한 뭐가 필요한가요?",
    "header": "Quiz: 스킬 구조",
    "options": [
      {"label": "SKILL.md 파일 하나", "description": ".claude/skills/이름/SKILL.md"},
      {"label": "Python 스크립트", "description": "코딩이 필요하지 않습니다"},
      {"label": "특별한 설치 과정", "description": "파일 하나만 있으면 됩니다"}
    ],
    "multiSelect": false
  }]
})
```

정답: 1번. `.claude/skills/이름/SKILL.md` 파일 하나만 있으면 스킬이 됩니다. 코딩이 필요 없습니다.

```json
AskUserQuestion({
  "questions": [{
    "question": "Day 2를 마치셨습니다! MCP로 도구를 연결하고, 나만의 스킬 뼈대를 만들었습니다. Day 3에서는 이 스킬을 완성합니다.",
    "header": "Day 2 완료 🎉",
    "options": [
      {"label": "수고했어요!", "description": "Day 3에서 만나요"}
    ],
    "multiSelect": false
  }]
})
```
