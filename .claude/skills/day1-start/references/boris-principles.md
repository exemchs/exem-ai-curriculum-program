# Boris Cherny의 Claude Code 워크플로우

> Claude Code를 만든 Boris Cherny (Head of Claude Code, Anthropic)의 핵심 원칙.
> 이 내용은 AX Camp 전체 커리큘럼에서 반복 적용됩니다.

---

## 6가지 핵심 원칙

### 1. Plan 먼저, 실행은 나중에

Shift+Tab을 두 번 누르면 **Plan Mode**로 전환됩니다.
Claude와 계획을 충분히 논의한 뒤, 만족스러우면 그때 실행합니다.

Boris: "Plan mode can 2-3x success rates if you align on the plan first."

**실천법:**
- 복잡한 작업은 반드시 Plan Mode로 시작
- 계획이 마음에 들면 Auto-accept으로 전환
- 삐뚤어지면 다시 Plan Mode로 돌아가기

**Day 3에서 직접 실습합니다.**

---

### 2. CLAUDE.md에 규칙을 적어라

팀의 규칙, 자주 하는 실수, 스타일 가이드를 CLAUDE.md에 적으면 Claude가 매번 읽고 따릅니다.

Boris: "Anytime we see Claude do something incorrectly we add it to the CLAUDE.md, so Claude knows not to do it next time."

**실천법:**
- Claude가 실수하면 → "CLAUDE.md에 추가해서 다시는 이 실수 안 하게 해줘"
- 시간이 지나면 실수율이 눈에 띄게 감소
- 팀 전체가 하나의 CLAUDE.md를 git으로 공유

**Day 1 Block 2에서 직접 만듭니다.**

---

### 3. 검증 루프를 줘라

Claude에게 결과를 스스로 확인할 방법을 주면 품질이 2-3배 올라갑니다.

Boris: "Give Claude a way to verify its work. If Claude has that feedback loop, it will 2-3x the quality of the final result."

**검증 방법 예시:**
| 작업 | 검증 루프 |
|------|-----------|
| 코드 작성 | "테스트를 실행해서 통과하는지 확인해" |
| 웹 페이지 | "브라우저에서 열어서 스크린샷 확인해" |
| 문서 작성 | "오타나 논리 오류 없는지 스스로 검토해" |
| 데이터 분석 | "결과가 맞는지 다른 방법으로 교차 검증해" |

**Day 3 Block 2에서 실습합니다.**

---

### 4. 반복은 자동화하라

매일 하는 작업은 슬래시 명령(Skill)으로 만드세요.

Boris 팀 사례:
- `/techdebt` — 세션 끝에 중복 코드 찾아 제거
- 7일치 Slack, GDrive, Asana, GitHub을 한 번에 동기화하는 커맨드 (EXEM에서는 Mattermost, Notion, ClickUp 등으로 대체)
- dbt 모델을 작성하고 테스트하는 analytics-engineer 에이전트

**실천법:**
- "이 작업 또 하고 있네?" → Skill로 만들기
- `.claude/commands/`에 저장하면 팀 공유 가능

**Day 3~4에서 직접 만듭니다.**

---

### 5. 구체적으로 말하라

모호하게 말하면 모호한 결과가 나옵니다.

| 나쁜 프롬프트 | 좋은 프롬프트 |
|---|---|
| "웹사이트 만들어줘" | "Next.js로 다크모드 랜딩 페이지를 만들어줘" |
| "버그 고쳐줘" | "로그인 버튼 클릭 시 500 에러가 나는데, auth 미들웨어를 확인해줘" |
| "보고서 써줘" | "이번 주 매출 데이터를 표로 정리하고, 전주 대비 증감률을 포함해줘" |

Boris 팀 팁:
- "Don't accept first solution. Push Claude to do better."
- 첫 결과에 만족하지 말고, Claude에게 더 나은 버전을 요청하세요
- 평범한 수정 후: "지금 알고 있는 걸 바탕으로 처음부터 다시 깔끔하게 만들어줘"

**Day 1 Block 1에서 체험합니다.**

---

### 6. 여러 Claude를 동시에

하나의 Claude로 순차 작업하지 마세요.

Boris의 셋업:
- 터미널 5개에 각각 독립 Claude 세션
- claude.ai/code에서 5~10개 추가 세션
- 아침에 모바일에서 시작 → 데스크톱으로 이관

**비전공자를 위한 시작:**
- 처음에는 2개로 시작 (터미널 1개 + claude.ai 1개)
- 하나가 작업하는 동안 다른 하나에 새 작업 지시
- 익숙해지면 점점 늘리기

**Day 4에서 Multi-agent 패턴을 실습합니다.**

---

## 추가 팁 (고급)

### Subagent 활용

프롬프트에 "use subagents"만 추가하면 Claude가 알아서 병렬 처리합니다.

활용 패턴:
- 여러 소스에서 동시 정보 수집
- 대립 관점(감사자 vs 옹호자)으로 정확성 향상
- 10개 이상 에이전트로 대규모 마이그레이션 병렬 처리

### PostToolUse Hook

코드 생성 후 자동으로 포맷팅하는 Hook 설정:
```json
{
  "hooks": {
    "PostToolUse": [{
      "command": "bun run format || true"
    }]
  }
}
```

### 권한 사전 승인

`/permissions`로 자주 쓰는 명령을 미리 승인해두면 작업 흐름이 끊기지 않습니다.
`--dangerously-skip-permissions` 대신 안전하게 관리하세요.

---

## Boris의 핵심 철학

> "What's better than doing something? Having Claude do it."

> "Experiment with the tools, don't be scared of them. Just dive in."

> "Coding is largely solved. The title software engineer is going to start to go away, replaced by 'builder'."

---

*출처: Boris Cherny Threads, Lenny's Newsletter 인터뷰 (2026)*
