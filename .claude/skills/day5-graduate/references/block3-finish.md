# Block 3: 졸업

## EXPLAIN

### 5일간 만든 것

```
📁 .claude/skills/
├── day1~5 AX Camp 스킬 (설치한 것)
├── context-sync/    ← Day 2~3에서 만든 것
├── wrap/            ← Day 4에서 만든 것
├── digest/          ← Day 4에서 만든 것
└── [졸업 프로젝트]/   ← Day 5에서 만든 것
```

### 5일 전과 지금

| Before | After |
|--------|-------|
| Claude Code가 뭔지 몰랐음 | 나만의 스킬 4개를 만들 수 있음 |
| 터미널이 무서웠음 | `/명령어` 한 줄로 업무 자동화 |
| AI는 채팅만 하는 줄 | MCP로 외부 도구 연결, Subagent로 병렬 작업 |
| 매번 같은 설명 반복 | CLAUDE.md로 한번 설정하면 끝 |

### 다음 단계

캠프는 끝나지만 시작입니다:

1. **매일 쓰기**: 만든 스킬을 실제 업무에 매일 사용하세요
2. **개선하기**: 쓰다 보면 고칠 점이 보입니다. Claude에게 수정 요청하세요
3. **공유하기**: 좋은 스킬은 팀원에게 공유하세요
4. **새로 만들기**: 새로운 반복 업무가 보이면 새 스킬을 만드세요

### 유용한 리소스

| 리소스 | 용도 |
|--------|------|
| Claude Code 공식 문서 | https://code.claude.com/docs/ko |
| AX Camp 원본 | https://github.com/anthropics/courses |
| EXEM 디자인 시스템 | 사내 프론트엔드 프로젝트 참고 |

### 도움이 필요할 때

```
Claude Code에서 [질문 내용]이 궁금해
```

모르는 게 있으면 Claude에게 물어보세요. 그게 가장 빠릅니다.

## EXECUTE

마지막 실습:

```
이번 캠프에서 배운 것과 만든 스킬들을 정리한
"나의 AX Camp 졸업 보고서"를 만들어줘.

포함할 내용:
- 5일간 배운 핵심 개념 요약
- 내가 만든 스킬 목록과 각 스킬의 기능
- 졸업 프로젝트 소개
- 앞으로 EXEM 업무에 적용할 계획
```

## QUIZ

```json
AskUserQuestion({
  "questions": [{
    "question": "AX Camp을 수료하셨습니다!",
    "header": "🎓 졸업을 축하합니다!",
    "options": [
      {"label": "감사합니다! 앞으로 잘 활용하겠습니다", "description": "AI Native의 시작입니다"},
      {"label": "더 배우고 싶어요", "description": "원본 캠프(camp-1)의 고급 과정을 추천합니다"},
      {"label": "동료에게 추천하고 싶어요", "description": "이 캠프 스킬을 공유해주세요!"}
    ],
    "multiSelect": false
  }]
})
```

> 수료가 아니라 시작입니다. Claude Code라는 도구를 다루는 EXEM의 새로운 일원이 되셨습니다.
