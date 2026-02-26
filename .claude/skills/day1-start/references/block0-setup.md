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

### 사전 설치 확인

README의 Step 1~4를 이미 완료했다면 넘어가세요.
아직이라면 README를 먼저 따라해주세요. 여기서는 요약만 합니다.

| 확인 항목 | 확인 방법 | 안 되면? |
|-----------|----------|---------|
| Git | 터미널에 `git --version` | Mac: `xcode-select --install` / Windows: git-scm.com 설치 |
| Node.js | 터미널에 `node --version` | nodejs.org에서 LTS 설치 (Day 2 MCP 서버에 필요) |
| Cursor | 실행되는지 확인 | cursor.com에서 다운로드 |

> Node.js는 Claude Code 자체에는 불필요하지만, Day 2에서 Notion 등 외부 도구를 연결(MCP)할 때 필요합니다. 미리 설치해두세요.

### Claude Code 설치

터미널에 아래 명령어를 **복사해서 붙여넣고** Enter를 누르세요:

| OS | 명령어 |
|----|--------|
| Mac / Linux | `curl -fsSL https://claude.ai/install.sh \| bash` |
| Windows | PowerShell에서 `irm https://claude.ai/install.ps1 \| iex` |

설치 후 **터미널을 껐다 다시 열어야** `claude` 명령이 인식됩니다.

> Windows에서 스크립트 실행이 차단되면:
> `Set-ExecutionPolicy RemoteSigned -Scope CurrentUser` 를 먼저 실행하세요.

### Claude Code 실행

터미널에 `claude`를 입력하고 Enter.
브라우저가 열리면서 Anthropic 계정 로그인을 안내합니다. 로그인하면 준비 완료!

| 문제 | 해결 |
|------|------|
| claude 명령 안 됨 | 터미널을 껐다 다시 열기 |
| Mac 보안 경고 | 시스템 설정 → 개인 정보 보호 및 보안 → "확인 없이 열기" |
| 로그인 후 사용 불가 | Anthropic 구독(Pro/Max) 활성화 여부 확인 |

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

1. **사전 확인**: `git --version`과 `node --version`이 동작하는지 확인 (안 되면 위 표 참고)
2. **Claude Code 설치**: 위 명령어 복사 → 터미널에 붙여넣기 → Enter
3. **터미널 재시작**: 터미널을 껐다 다시 열기
4. **첫 실행**: 터미널에서 `claude` 입력
5. **로그인**: 브라우저에서 Anthropic 계정 연결
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
