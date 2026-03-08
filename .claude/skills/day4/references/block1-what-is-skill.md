# Block 1: Skill 깊이 파기


## EXPLAIN

## [1] Skill — 내가 직접 만드는 자동화
═══════════════════════════════

Day 3에서 Skill 개념과 플러그인 생태계를 배웠죠?
오늘은 **직접 만들어봅니다**.

### 복습: Skill = 요리 레시피

  🍳 레시피 없을 때               📖 레시피 있을 때
  ─────────────                  ─────────────
  매번 "양파 썰고, 볶고,          "파스타 레시피대로 해"
  소스 넣고, 끓이고..."           → 한마디로 끝
  → 매번 처음부터 설명            → 저장된 절차대로 실행


### Skill의 구조

```
.claude/skills/
  └── 내스킬/
      ├── SKILL.md          ← 레시피 제목 + 설명
      └── references/
          └── 상세지시.md     ← 상세 레시피
```

  SKILL.md       = 언제, 어떻게 실행하는지
  references/    = 구체적인 지시사항, 예시, 템플릿


### 이 커리큘럼 자체가 Skill의 실물 예시

```
.claude/skills/
  ├── day0-orientation/   ← /day0
  ├── day1/               ← /day1
  ├── day2/               ← /day2
  ├── day3/               ← /day3
  ├── day4/               ← /day4 (지금!)
  └── day5/               ← /day5
```

Day 3에서 본 GSD 같은 플러그인도 결국 이 구조입니다.
구조를 이해하면 **남이 만든 것을 쓰는 것**에서
**내가 만드는 것**으로 넘어갈 수 있습니다.

Boris Cherny(Claude Code 창시자)의 말:
"매일 반복하는 inner loop 워크플로우에 슬래시 명령을 쓴다."

───────────────────────────────


## EXECUTE

### Skill 구조 직접 분석

1. Day 3의 SKILL.md를 읽어봅시다:
```
.claude/skills/day3/SKILL.md 파일을 읽어서 보여줘
```

2. reference 파일도 하나 읽어봅시다:
```
.claude/skills/day3/references/block1-mcp-concept.md 읽어줘
```

3. 패턴을 파악해봅시다:
```
SKILL.md에서 어떤 정보를 정의하고 있는지 정리해줘.
reference 파일과의 관계도 설명해줘.
```

💡 이 구조를 이해하면 다음 Block에서
   내 업무에 맞는 Skill을 직접 만들 수 있습니다.

───────────────────────────────
