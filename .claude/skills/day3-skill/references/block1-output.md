# Block 1: 출력 포맷 + 마무리

## EXPLAIN

### 출력이 왜 중요한가?

스킬이 수집한 정보를 어떤 형태로 보여줄지 결정합니다.
같은 내용이라도 형식에 따라 유용함이 완전히 달라집니다.

| 포맷 | 용도 | 예시 |
|------|------|------|
| Markdown 문서 | 보고서, 공유 | 주간 보고서.md |
| 터미널 출력 | 빠른 확인 | 바로 화면에 표시 |
| 파일 저장 | 기록 보관 | reports/2026-02-26.md |

### SKILL.md에 출력 포맷 지정하기

```markdown
## 출력 형식

아래 포맷으로 Markdown 문서를 생성하여 `reports/` 폴더에 저장한다.
파일명: `YYYY-MM-DD-weekly.md`

### 템플릿

# 주간 현황 ({날짜})

## 주요 이슈
- {Mattermost에서 수집한 주요 이슈}

## 진행 중인 작업
- {Notion/ClickUp에서 수집한 작업 현황}

## 이번 주 일정
- {Calendar에서 수집한 일정}

## 액션 아이템
- {종합하여 도출한 할 일}
```

### 스킬 설명문(description) 다듬기

frontmatter의 `description`은 Claude가 스킬 목록에서 보여주는 한 줄 설명입니다.
구체적일수록 Claude가 언제 이 스킬을 제안할지 잘 판단합니다.

나쁜 예: `description: 업무 도구`
좋은 예: `description: Mattermost와 Notion에서 이번 주 업무 현황을 수집하여 주간 보고서를 자동 생성한다`

## EXECUTE

1. **출력 포맷 추가**: 스킬의 SKILL.md에 출력 형식 섹션을 추가하세요
```
내 스킬의 SKILL.md에 출력 형식 섹션을 추가해줘.
Markdown 문서로 저장하고, 날짜가 포함된 파일명을 사용하게 해줘.
```

2. **description 다듬기**: frontmatter의 description을 구체적으로 수정하세요
```
내 스킬의 description을 더 구체적으로 다듬어줘
```

## QUIZ

```json
AskUserQuestion({
  "questions": [{
    "question": "좋은 스킬 description의 조건은?",
    "header": "Quiz: Description",
    "options": [
      {"label": "무엇을 수집하고 어떤 결과를 만드는지 구체적으로", "description": "Claude가 스킬 제안 시 사용"},
      {"label": "최대한 짧게 한 단어로", "description": "너무 짧으면 Claude가 언제 쓸지 모릅니다"},
      {"label": "영어로 작성", "description": "한국어도 됩니다"}
    ],
    "multiSelect": false
  }]
})
```

정답: 1번. **무엇을 하고 어떤 결과를 만드는지** 구체적으로 작성해야 Claude가 적절한 시점에 스킬을 제안합니다.
