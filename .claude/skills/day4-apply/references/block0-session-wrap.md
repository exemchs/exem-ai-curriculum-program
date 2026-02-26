# Block 0: Session Wrap

## EXPLAIN

> 📖 참고: session-wrap은 Multi-agent 패턴의 대표 예시입니다

### Session Wrap이란?

Claude Code로 작업한 세션(대화)을 마칠 때, 자동으로 정리하는 스킬입니다.

```
/wrap 실행
  │
  ├── Agent 1 → 이 세션에서 뭘 했는지 요약
  ├── Agent 2 → 다음에 할 일 정리
  └── Agent 3 → 배운 것/메모할 것 추출
  │
  ▼
📄 세션 정리 문서 자동 생성
```

### 왜 필요한가?

| 상황 | Session Wrap 없이 | Session Wrap 있으면 |
|------|---|---|
| 퇴근 전 | "오늘 뭐했더라..." 기억에 의존 | `/wrap` → 자동 정리 |
| 다음 날 출근 | "어디까지 했지..." | 정리 문서 보고 바로 이어서 |
| 인수인계 | 장문의 설명 필요 | 문서 공유 한 장 |

### EXEM에서의 활용

- 개발: 코딩 세션 마무리 시 변경사항 + 다음 할 일 자동 정리
- 기획: 리서치 세션 마무리 시 발견한 것 + 결론 정리
- 공통: 회의 후 액션 아이템 자동 추출

### Multi-agent 패턴

Session Wrap은 **여러 Agent가 각자 역할을 맡아 동시에 작업**하는 패턴입니다:

```markdown
## 실행 흐름

다음 Agent를 병렬로 실행한다:

### Agent 1: 요약
이 세션에서 수행한 작업을 시간순으로 정리한다.

### Agent 2: 다음 작업
완료하지 못한 작업, 다음에 해야 할 일을 목록으로 정리한다.

### Agent 3: 학습
새로 배운 것, 기억할 패턴, 주의사항을 추출한다.

모든 Agent 결과를 종합하여 세션 정리 문서를 생성한다.
```

## EXECUTE

Session Wrap 스킬을 만들어보세요:

```
.claude/skills/에 session-wrap 스킬을 만들어줘.
이름은 /wrap으로.

이 세션에서 한 작업 요약, 다음 할 일, 배운 것을
각각 Agent가 병렬로 수집해서 하나의 정리 문서를 만드는 스킬이야.

출력은 Markdown으로, reports/ 폴더에 날짜 포함 파일명으로 저장해줘.
```

## QUIZ

```json
AskUserQuestion({
  "questions": [{
    "question": "Session Wrap에서 여러 Agent를 쓰는 이유는?",
    "header": "Quiz: Multi-agent",
    "options": [
      {"label": "각자 다른 관점으로 동시에 분석해서 빠르고 풍부함", "description": "병렬 실행 + 역할 분담"},
      {"label": "하나가 실패해도 다른 게 작동하니까", "description": "안정성이 아니라 속도와 품질입니다"},
      {"label": "API 호출 제한을 피하려고", "description": "기술적 이유가 아닙니다"}
    ],
    "multiSelect": false
  }]
})
```

정답: 1번. 여러 Agent가 **각자 다른 관점으로 동시에 분석**하면 빠르고 풍부한 결과를 얻습니다.
