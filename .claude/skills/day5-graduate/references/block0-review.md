# Block 0: 5일간 배운 것 정리

## EXPLAIN

### 여기까지 오셨습니다

```
Day 1: 시작하기
├── Claude Code 설치 + 첫 대화
├── CLAUDE.md로 나의 규칙 만들기
└── 핵심 기능 4가지 이해 (Skill, MCP, Subagent, Hook)

Day 2: 외부 도구 연결
├── MCP로 Mattermost/Notion 등 연결
└── Context Sync 스킬 뼈대 제작

Day 3: 나만의 스킬 완성
├── Subagent로 병렬 수집
├── 출력 포맷 설정
└── 스킬 실행 + 검증

Day 4: 실무 적용
├── Session Wrap 스킬 제작
└── Content Digest 스킬 제작

Day 5: 졸업 ← 지금 여기
└── 졸업 프로젝트 완성
```

### 내가 만든 것들

| 스킬 | 기능 | 핵심 기술 |
|------|------|-----------|
| Context Sync | 여러 도구에서 정보 수집 | MCP + Subagent |
| Session Wrap | 작업 세션 자동 정리 | Multi-agent |
| Content Digest | 콘텐츠 소화 + 학습 | WebFetch + Quiz |

### 핵심 개념 요약

| 개념 | 한 줄 정리 |
|------|-----------|
| CLAUDE.md | 매 대화 시작 시 자동으로 읽히는 규칙서 |
| Skill | `/명령어`로 실행하는 나만의 자동화 |
| MCP | 외부 도구를 Claude에 연결하는 표준 규격 |
| Subagent | 여러 AI가 동시에 작업하는 팀워크 |
| AskUserQuestion | Claude가 추측 대신 질문하게 하는 도구 |

## EXECUTE

아래 명령을 실행해서 자신이 만든 스킬들을 확인하세요:

```
.claude/skills/ 폴더에 내가 만든 스킬들을 전부 보여줘.
각 스킬의 이름, description, 핵심 기능을 표로 정리해줘.
```

## QUIZ

```json
AskUserQuestion({
  "questions": [{
    "question": "5일간 가장 유용하다고 느낀 기능은?",
    "header": "5일 돌아보기",
    "options": [
      {"label": "CLAUDE.md — 한번 설정하면 매번 자동", "description": "규칙 반복 불필요"},
      {"label": "Skill — 나만의 자동화 명령어", "description": "반복 업무 제거"},
      {"label": "MCP — 외부 도구 연결", "description": "수동 복붙 제거"},
      {"label": "Subagent — 병렬 작업", "description": "시간 절약"}
    ],
    "multiSelect": false
  }]
})
```

> 정답이 없는 질문입니다. 자신에게 가장 유용한 것이 정답입니다.
