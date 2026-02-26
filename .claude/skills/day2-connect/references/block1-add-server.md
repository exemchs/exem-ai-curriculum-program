# Block 1: MCP 서버 연결

## EXPLAIN

> 📖 공식 문서: https://code.claude.com/docs/ko/integrations/mcp

### 서버 추가하는 법

`claude mcp add` 명령어를 터미널에서 실행합니다.

```bash
claude mcp add [서버이름] -- [실행명령]
```

### 실제 예시: Notion 연결

```bash
claude mcp add notion -- npx -y @anthropic-ai/claude-code-notion-mcp
```

이 한 줄이면 Claude가 Notion을 직접 검색하고 읽을 수 있습니다.

### Plugin으로 더 쉽게

Claude Code에는 이미 많은 MCP 서버가 Plugin으로 준비되어 있습니다:

```
/plugin
```

Plugin 목록에서 필요한 걸 선택하면 자동으로 MCP 서버가 설치됩니다.

### 연결 확인

```
/mcp
```

연결된 서버 목록과 사용 가능한 도구가 표시됩니다.

### 주의사항

| 주의 | 설명 |
|------|------|
| API 키 | 일부 서버는 API 키가 필요합니다 (환경변수로 설정) |
| 권한 | Claude가 도구를 쓸 때 승인을 요청합니다 |
| 범위 | 프로젝트 단위(.mcp.json) 또는 글로벌(~/.claude/) 설정 가능 |

## EXECUTE

1. **Plugin 탐색**: `/plugin`을 실행해서 어떤 MCP 서버가 있는지 둘러보세요
2. **하나 연결**: Notion 또는 관심있는 서버를 하나 연결하세요
3. **확인**: `/mcp`로 연결 상태 확인
4. **테스트**: 연결한 도구에 대해 Claude에게 질문해보세요

> 어떤 서버를 연결할지 모르겠으면 Notion부터 시작하세요. 가장 범용적입니다.

## QUIZ

```json
AskUserQuestion({
  "questions": [{
    "question": "MCP 서버를 추가하는 가장 쉬운 방법은?",
    "header": "Quiz: MCP 서버 추가",
    "options": [
      {"label": "/plugin에서 선택", "description": "이미 준비된 서버를 골라서 설치"},
      {"label": "코드를 직접 작성", "description": "필요할 수도 있지만 가장 쉬운 방법은 아닙니다"},
      {"label": "설정 파일을 수동 편집", "description": "가능하지만 가장 쉬운 방법은 아닙니다"}
    ],
    "multiSelect": false
  }]
})
```

정답: 1번. `/plugin`에서 선택하는 게 가장 쉽습니다. 고급 사용자는 `claude mcp add`로 직접 추가할 수도 있습니다.
