# Block 1: 첫 대화 + 체험

## EXPLAIN

> 📖 공식 문서: https://code.claude.com/docs/ko/quickstart

> 5일 후 모습을 먼저 맛봅니다. 외우지 않습니다. 느끼기만 하세요.

### Before / After

| 지금 (Before) | 5일 후 (After) |
|---|---|
| 보고서 쓰려면 자료 찾기 30분 | "이번 주 보고서 써줘" 한 마디 |
| "이거 해줘" → 뭘 원하는지 모호 | Claude가 질문하며 명확화 |
| 기능 외우려고 문서 뒤지기 | 모르면 Claude에게 물어보기 |
| EXEM 제품 문서 정리에 하루 | 자동 수집 + 정리 |

### 체험 1: 모호한 요청 vs 명확한 요청

먼저 이렇게 요청해보세요:
```
우리 팀 업무를 개선해줘
```
Claude가 혼자 추측해서 결과를 내놓을 겁니다.

이번엔 다르게:
```
우리 팀 업무를 개선해줘. 모호한 부분은 AskUserQuestion으로 질문해서 명확하게 만들어
```
Claude가 "어떤 팀인가요?", "몇 명인가요?", "가장 큰 병목은?" 같은 **선택지를 제시하며 질문**합니다.

핵심: **AskUserQuestion**을 쓰면 Claude가 추측 대신 질문합니다. 결과가 완전히 달라집니다.

### 체험 2: Claude에게 물어보기

```
Claude Code에서 Skill이 뭐야? 한 줄로 설명해줘
```

핵심: 기능을 다 외울 필요 없습니다. **모르면 Claude에게 물어보면 됩니다.**

### 체험 3: 실제 업무 맛보기

```
내가 EXEM에서 [나의 업무]를 하고 있는데, Claude Code로 자동화할 수 있는 게 뭐가 있을지 5가지만 제안해줘
```

[나의 업무] 자리에 실제 자신의 업무를 넣으세요. QA, 마케팅, 기획, 개발 뭐든 됩니다.

## EXECUTE

3가지 체험을 직접 실행하세요:

1. **체험 1**: 모호한 요청 → AskUserQuestion 버전 재요청 → 차이 체험
2. **체험 2**: Claude Code 자체에 대해 질문
3. **체험 3**: 내 업무에 Claude Code 적용 가능성 탐색

## QUIZ

```json
AskUserQuestion({
  "questions": [{
    "question": "3가지 체험 중 가장 인상적이었던 건?",
    "header": "체험 소감",
    "options": [
      {"label": "체험 1: AskUserQuestion", "description": "Claude가 질문으로 명확화하는 것"},
      {"label": "체험 2: Claude에게 물어보기", "description": "모르면 물어보면 되는 것"},
      {"label": "체험 3: 내 업무 자동화", "description": "실제 업무에 적용 가능성"}
    ],
    "multiSelect": false
  }]
})
```

> 정답이 없는 체험 확인입니다.
