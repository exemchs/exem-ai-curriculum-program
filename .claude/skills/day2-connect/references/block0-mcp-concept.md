# Block 0: MCP 개념 이해

## EXPLAIN

> 📖 공식 문서: https://code.claude.com/docs/ko/integrations/mcp

### MCP가 뭔가요?

**Model Context Protocol** — AI가 외부 도구를 사용할 수 있게 해주는 표준 규격입니다.

USB-C 비유로 이해하면 쉽습니다:

```
USB-C 포트 하나로:          MCP 하나로:
├── 충전기 연결              ├── Mattermost 연결
├── 모니터 연결              ├── Notion 연결
├── 외장하드 연결            ├── ClickUp 연결
└── 어떤 기기든 OK           └── 어떤 도구든 OK
```

USB-C가 모든 기기를 하나의 포트로 연결하듯, MCP는 모든 외부 도구를 하나의 규격으로 Claude에 연결합니다.

### 연결하면 뭐가 달라지나요?

| MCP 없이 | MCP 연결 후 |
|----------|------------|
| Mattermost 열고 → 메시지 복사 → Claude에 붙여넣기 | "이번 주 Mattermost 요약해줘" 한 마디 |
| Notion 열고 → 페이지 찾고 → 내용 복사 | "Notion에서 회의록 가져와" 한 마디 |
| 데이터를 수동으로 옮기며 정리 | Claude가 직접 접근해서 자동 처리 |

### EXEM에서 유용한 MCP 서버

| 도구 | 용도 | 누가 | 비고 |
|------|------|------|------|
| **Notion** | 문서 검색, 업데이트 | 전 직원 | 가장 안정적, 추천 |
| **Mattermost** | 채널 메시지 수집, 요약 | 전 직원 | 커뮤니티 버전 사용 중 |
| **GitHub** | 코드, PR, 이슈 | 엔지니어 | |
| **Google Calendar** | 일정 확인 | 전 직원 | |
| **ClickUp** | 태스크 관리 | 전 직원 | API 안정성 이슈 — 체험 수준만 권장 |

## EXECUTE

Claude에게 직접 물어보세요:

```
MCP 서버를 추가하는 방법을 알려줘. 실제로 하나 추가해볼 수 있게 단계별로 안내해줘.
```

그리고 현재 연결된 MCP 서버를 확인하세요:

```
/mcp
```

## QUIZ

```json
AskUserQuestion({
  "questions": [{
    "question": "MCP를 한 마디로 설명하면?",
    "header": "Quiz: MCP",
    "options": [
      {"label": "AI가 외부 도구를 사용할 수 있게 해주는 규격", "description": "USB-C처럼 모든 도구를 하나의 표준으로 연결"},
      {"label": "AI 모델을 학습시키는 방법", "description": "그건 Fine-tuning입니다"},
      {"label": "채팅 프로토콜", "description": "그건 일반 채팅입니다"}
    ],
    "multiSelect": false
  }]
})
```

정답: 1번. MCP는 **AI가 외부 도구를 사용할 수 있게 해주는 표준 규격**입니다.
