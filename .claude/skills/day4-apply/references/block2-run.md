# Block 2: 두 스킬 실행 + 검증

## EXPLAIN

### 오늘 만든 것 정리

| 스킬 | 명령어 | 기능 |
|------|--------|------|
| Session Wrap | `/wrap` | 작업 세션 자동 정리 |
| Content Digest | `/digest` | 콘텐츠 소화 + Quiz-First |

### 실행 전 체크리스트

| 확인 | 방법 |
|------|------|
| 스킬이 인식되는가? | `/` 입력 후 목록에 나오는지 |
| SKILL.md가 있는가? | `.claude/skills/스킬이름/SKILL.md` 존재 확인 |
| frontmatter가 있는가? | `---` 블록에 name, description 있는지 |

## EXECUTE

두 스킬을 각각 실행해보세요:

**1. Session Wrap 테스트**
```
/wrap
```
지금까지의 캠프 세션을 정리해봅니다.

**2. Content Digest 테스트**

아래 중 하나를 선택해서 테스트하세요:
```
/digest
```
그리고 URL을 물어보면:
- 관심있는 기술 블로그 URL
- YouTube 영상 URL
- 아무 기사 URL

> 두 스킬 모두 한번에 완벽할 필요 없습니다.
> 결과를 보고 Claude에게 "이 부분을 수정해줘"라고 요청하면 됩니다.

## QUIZ

```json
AskUserQuestion({
  "questions": [{
    "question": "Day 4를 마치셨습니다! 지금까지 캠프에서 만든 스킬을 정리해볼까요?",
    "header": "Day 4 완료 🎉",
    "options": [
      {"label": "Context Sync + Session Wrap + Content Digest", "description": "벌써 3개 스킬을 만들었습니다!"},
      {"label": "하나도 완성 못한 것 같아요", "description": "괜찮습니다. 뼈대라도 만들었으면 성과입니다"},
      {"label": "더 만들고 싶어요", "description": "그 열정! Day 5에서 졸업 프로젝트를 합니다"}
    ],
    "multiSelect": false
  }]
})
```

> Day 5에서는 지금까지 배운 것을 종합하여 EXEM 업무에 맞는 졸업 프로젝트를 완성합니다.
