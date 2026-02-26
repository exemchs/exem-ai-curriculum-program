# Block 2: CLAUDE.md — 나의 규칙서

## EXPLAIN

> 📖 공식 문서: https://code.claude.com/docs/ko/memory

### CLAUDE.md가 뭔가요?

Claude Code가 **매 대화 시작할 때 자동으로 읽는 규칙서**입니다.

비유: 새로 온 인턴에게 매번 "우리 팀은 이렇게 일해"를 설명하는 대신, 문서 하나 건네주는 것.

```
대화 시작
  │
  ▼
┌─────────────┐     ┌─────────────┐
│ CLAUDE.md   │────▶│ Claude가     │────▶ 규칙을 아는 상태로 대화
│ (규칙서)     │     │ 자동으로 읽음 │
└─────────────┘     └─────────────┘
```

### 뭘 적나요?

| 종류 | 예시 |
|------|------|
| 소통 스타일 | "한국어로 답해줘", "존댓말 써줘" |
| 내 정보 | "나는 EXEM BX팀 소속이야" |
| 작업 규칙 | "커밋 메시지는 한국어로" |
| 프로젝트 정보 | "이 프로젝트는 Next.js로 되어있어" |

### EXEM 예시

EXEM에서 일하는 분이라면 이런 내용을 넣을 수 있습니다:

```markdown
# CLAUDE.md

## 나
- 이름: [이름]
- 소속: EXEM [팀명]
- 역할: [역할]

## 소통
- 한국어 응답 기본
- 번호 리스트, 표 활용, 간결하게

## EXEM 맥락
- 주력 제품: exemONE(통합 모니터링), MaxGauge(DB), InterMax(APM)
- AI 제품: XAIOps(AIOps), eXemble(LLMOps), Aster AI
- 경쟁사: Whatap, Datadog, Sherpasoft
```

### 두 가지 명령어

| 명령어 | 기능 |
|--------|------|
| `/init` | 현재 폴더를 분석해서 CLAUDE.md 자동 생성 |
| `/memory` | 대화 중 발견한 선호사항을 영구 기억으로 저장 |

## EXECUTE

두 가지를 순서대로 실행하세요:

**1단계: CLAUDE.md 만들기**
```
/init
```
Claude가 현재 폴더를 분석해서 CLAUDE.md를 자동 생성합니다.
생성된 파일을 확인하고, 위 EXEM 예시를 참고해서 자신의 정보를 추가해보세요:
```
CLAUDE.md에 내 정보를 추가해줘. 이름은 [이름], EXEM [팀명] 소속이야.
한국어로 답해주고, 표를 많이 쓰는 걸 좋아해.
```

**2단계: 기억 저장 테스트**
```
/memory
```
"항상 존댓말로 해줘" 같은 규칙을 저장해보세요.

**3단계: 확인**

Claude Code를 `/clear`로 대화를 초기화한 뒤, 다시 말을 걸어보세요.
방금 설정한 규칙이 적용되는지 확인합니다.

## QUIZ

```json
AskUserQuestion({
  "questions": [{
    "question": "CLAUDE.md는 언제 읽히나요?",
    "header": "Quiz: CLAUDE.md",
    "options": [
      {"label": "매 대화 시작할 때 자동으로", "description": "Claude가 세션 시작 시 항상 읽습니다"},
      {"label": "내가 '읽어'라고 할 때만", "description": "수동이 아닙니다"},
      {"label": "하루에 한 번", "description": "매 대화마다 읽습니다"}
    ],
    "multiSelect": false
  }]
})
```

정답: 1번. CLAUDE.md는 **매 대화가 시작될 때 자동으로** 읽힙니다.
그래서 한번 설정해두면 매번 반복해서 말할 필요가 없습니다.
