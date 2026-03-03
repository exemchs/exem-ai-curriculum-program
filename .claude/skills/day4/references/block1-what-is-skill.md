# Block 1: Skill이란


## EXPLAIN

## [1] Skill이란
═══════════════════════════════

Skill은 반복 업무를 `/명령어`로 저장하는 것입니다.

비유: 요리 레시피

  🍳 레시피 없을 때               📖 레시피 있을 때
  ─────────────                  ─────────────
  매번 "양파 썰고, 볶고,          "파스타 레시피대로 해"
  소스 넣고, 끓이고..."           → 한마디로 끝
  → 매번 처음부터 설명            → 저장된 절차대로 실행

Claude Code에서도 동일합니다:

  Skill 없을 때                   Skill 있을 때
  ─────────────                  ─────────────
  매번 긴 요청을 타이핑           `/주간보고` 한마디
  매번 형식을 지정                 저장된 형식대로 자동
  사람마다 결과가 다름             누가 해도 같은 품질


### Skill의 구조

```
.claude/skills/
  └── 내스킬/
      ├── SKILL.md          ← 레시피 제목 + 설명
      └── references/
          └── 상세지시.md     ← 상세 레시피
```

  SKILL.md       = 레시피 이름, 언제 쓰는지, 대략적인 진행 방식
  references/    = 구체적인 지시사항, 예시, 템플릿

Boris Cherny(Claude Code 창시자)의 말:
"매일 반복하는 inner loop 워크플로우에 슬래시 명령을 쓴다."


### 지금 이 순간이 바로 Skill 실행 중

사실 여러분은 이미 Skill을 체험하고 있습니다!
`/day4`를 입력한 것 자체가 Skill 호출입니다.

이 커리큘럼 전체가 Skill로 만들어져 있습니다:
```
.claude/skills/
  ├── day0-orientation/   ← /day0
  ├── day1/               ← /day1
  ├── day2/               ← /day2
  ├── day3/               ← /day3
  ├── day4/               ← /day4 (지금!)
  └── day5/               ← /day5
```

───────────────────────────────


## EXECUTE

### Skill 구조 탐색

1. `.claude/skills/` 폴더를 직접 확인해봅시다:
```
이 프로젝트의 .claude/skills/ 폴더 구조를 보여줘
```

2. Skill 목록을 확인해봅시다:
```
이 프로젝트에서 사용할 수 있는 Skill 목록을 알려줘
```

3. 지금 실행 중인 Day 4의 SKILL.md를 읽어봅시다:
```
.claude/skills/day4/SKILL.md 파일을 읽어서 보여줘
```

💡 Skill이 어떻게 구성되어 있는지 직접 보면
   다음 Block에서 내 Skill을 만들 때 감이 잡힙니다.

───────────────────────────────


## QUIZ

```json
{
  "questions": [{
    "question": "Skill이 웹 ChatGPT에서 프롬프트를 저장하는 것과 다른 점은?",
    "header": "Skill 특징",
    "options": [
      {"label": "저장할 수 있는 글자 수가 더 많다", "description": "분량의 차이가 아닙니다"},
      {"label": "파일 접근 + 자동 로드 + 팀 공유 가능", "description": "정답! Skill은 파일을 읽고, 자동으로 로드되고, 팀과 공유됩니다"},
      {"label": "더 예쁜 형식으로 출력된다", "description": "형식의 차이가 아닙니다"},
      {"label": "AI가 더 똑똑하게 답한다", "description": "AI의 능력이 아니라 맥락의 차이입니다"}
    ],
    "multiSelect": false
  }]
}
```

> 정답: "파일 접근 + 자동 로드 + 팀 공유 가능"
> Skill은 프로젝트 안에 저장되므로 팀원이 같은 프로젝트를 열면 모두 사용 가능합니다.
