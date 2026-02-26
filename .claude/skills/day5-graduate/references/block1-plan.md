# Block 1: 졸업 프로젝트 기획

## EXPLAIN

### 졸업 프로젝트란?

자신의 EXEM 업무에 실제로 적용할 수 있는 **스킬 1개**를 만드는 것입니다.

조건:
- 실제 자기 업무에서 반복되는 작업을 자동화할 것
- Day 1~4에서 배운 기술을 1개 이상 활용할 것
- 다른 EXEM 동료에게 공유할 수 있을 것

### 아이디어 예시 (역할별)

| 역할 | 스킬 아이디어 | 활용 기술 |
|------|-------------|-----------|
| **개발** | `/code-review` — PR 자동 리뷰 요약 | GitHub MCP + Subagent |
| **개발** | `/db-health` — DB 성능 지표 자동 수집 | MCP + 출력 포맷 |
| **QA** | `/test-report` — 테스트 결과 자동 정리 | Subagent + 문서 생성 |
| **기획** | `/competitor-watch` — 경쟁사 동향 수집 | WebSearch + Digest |
| **마케팅** | `/content-plan` — 콘텐츠 캘린더 자동 생성 | Calendar MCP + 문서 |
| **영업** | `/client-prep` — 고객 미팅 사전 자료 정리 | Notion MCP + 요약 |
| **공통** | `/daily-standup` — 오늘 할 일 자동 정리 | Mattermost MCP + Calendar |
| **공통** | `/exem-news` — EXEM 관련 뉴스 자동 수집 | WebSearch + Digest |

### 기획 프레임

3가지만 정하면 됩니다:

1. **무엇을**: 어떤 반복 업무를 자동화?
2. **어떻게**: 어떤 기술을 활용? (MCP, Subagent, Digest 등)
3. **결과물**: 어떤 형태로 출력? (문서, 표, 파일)

## EXECUTE

졸업 프로젝트를 기획하세요. Claude에게 이렇게 요청하세요:

```
졸업 프로젝트를 기획하고 싶어.
나는 EXEM [팀명]에서 [역할]을 하고 있어.
반복되는 업무 중에 [가장 번거로운 업무]가 있는데,
이걸 Claude Code 스킬로 자동화하고 싶어.

1. 무엇을 자동화할지
2. 어떤 기술을 쓸지 (MCP, Subagent 등)
3. 결과물 형태

이 3가지를 AskUserQuestion으로 질문하면서 같이 정해줘.
```

## QUIZ

```json
AskUserQuestion({
  "questions": [{
    "question": "졸업 프로젝트 기획이 되었나요?",
    "header": "기획 확인",
    "options": [
      {"label": "네! 3가지 다 정했어요", "description": "Block 2에서 바로 제작합니다"},
      {"label": "대략 정했는데 확신이 없어요", "description": "괜찮습니다. 만들면서 조정하면 됩니다"},
      {"label": "아이디어가 안 떠올라요", "description": "위 예시 중 하나를 선택해서 시작해보세요"}
    ],
    "multiSelect": false
  }]
})
```
