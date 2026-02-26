# Block 0: 설치 + 첫 실행

## EXPLAIN

> 📖 공식 문서: https://code.claude.com/docs/ko/setup

### Claude Code가 뭔가요?

터미널(검은 화면)에서 동작하는 AI 비서입니다.
ChatGPT처럼 대화하지만, **내 컴퓨터의 파일을 직접 읽고 쓸 수 있다**는 게 다릅니다.

| ChatGPT/Claude 웹 | Claude Code |
|---|---|
| 브라우저에서 대화 | 터미널에서 대화 |
| 파일을 복붙해야 함 | 내 파일을 직접 읽고 수정 |
| 대화가 끝나면 잊음 | CLAUDE.md로 기억 유지 |
| 혼자 작업 | 여러 AI가 팀으로 협업 (Subagent) |

### 설치 — 4단계

#### 1단계: Cursor 에디터 설치

cursor.com에서 다운로드하세요.
Cursor는 파일을 눈으로 보면서 작업할 수 있는 에디터입니다.
코드를 모르는 분도 걱정 마세요. 파일 탐색기처럼 사용하면 됩니다.

```
cursor.com → Download → 설치 → 실행
```

#### 2단계: 터미널 열기

Cursor를 실행한 뒤, 상단 메뉴에서:
```
Terminal → New Terminal
```
아래쪽에 검은 창이 나타납니다. 이것이 **터미널**입니다.
여기에 명령어를 입력해서 Claude와 대화합니다.

#### 3단계: Claude Code 설치

터미널에 아래 명령어를 **복사해서 붙여넣고** Enter를 누르세요:

| OS | 명령어 |
|----|--------|
| Mac / Linux | `curl -fsSL https://claude.ai/install.sh \| bash` |
| Windows | PowerShell에서 `irm https://claude.ai/install.ps1 \| iex` |

Node.js 불필요. 한 줄이면 끝.

#### 4단계: Claude Code 실행

터미널에 `claude`를 입력하고 Enter.
Anthropic 계정으로 로그인하면 준비 완료!

| 문제 | 해결 |
|------|------|
| 권한 에러 (Mac) | 터미널을 관리자 권한으로 재실행 |
| claude 명령 안 됨 | 터미널을 껐다 다시 열기 |

### 첫 실행 설정

로그인이 끝나면:
```
/output-style
→ Explanatory 선택
```

Explanatory 모드에서는 Claude가 왜 그렇게 하는지 설명해줍니다.
배우는 단계에서 가장 좋습니다.

### Boris Cherny의 핵심 원칙

Claude Code를 만든 Boris Cherny가 강조하는 핵심 원칙 6가지입니다.
이 캠프 전체에서 계속 적용할 내용이니 기억해두세요:

| 원칙 | 설명 |
|------|------|
| **Plan 먼저** | 바로 실행하지 마세요. Plan Mode로 계획을 먼저 세우세요. |
| **CLAUDE.md에 규칙 적기** | 한번 적으면 Claude가 영원히 기억합니다. |
| **검증 루프** | Claude에게 스스로 확인할 방법을 주면 품질이 2-3배 올라갑니다. |
| **반복은 자동화** | 매일 하는 작업은 `/명령어`(Skill)로 만드세요. |
| **구체적으로 말하기** | "웹사이트 만들어줘"보다 "Next.js 다크모드 랜딩 페이지 만들어줘"가 10배 낫습니다. |
| **여러 Claude 동시에** | 하나로 순차 작업하지 마세요. 여러 세션을 동시에 돌리세요. |

> 이 원칙들은 Day 2~5에서 실제로 적용하며 체화합니다.

## EXECUTE

순서대로 실행하세요:

1. **Cursor 설치**: cursor.com에서 다운로드 → 설치 → 실행
2. **터미널 열기**: Cursor 메뉴 → Terminal → New Terminal
3. **Claude Code 설치**: 위 명령어 복사 → 터미널에 붙여넣기 → Enter
4. **첫 실행**: 터미널에서 `claude` 입력
5. **로그인**: Anthropic 계정 연결
6. **Output Style**: `/output-style` → Explanatory 선택
7. **첫 인사**: "안녕, 나는 [이름]이고 EXEM [팀명]에서 일해. 나한테 인사해줘"

## QUIZ

```json
AskUserQuestion({
  "questions": [{
    "question": "설치와 첫 실행까지 완료했나요?",
    "header": "Setup 확인",
    "options": [
      {"label": "완료!", "description": "Block 1로 이동"},
      {"label": "아직 진행 중", "description": "더 시간이 필요합니다"},
      {"label": "도움이 필요해요", "description": "설치나 실행에 문제 발생"}
    ],
    "multiSelect": false
  }]
})
```

> Block 0은 퀴즈 대신 완료 확인만 합니다.
