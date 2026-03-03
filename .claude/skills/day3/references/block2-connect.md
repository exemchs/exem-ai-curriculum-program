# Block 2: 실제 연결


## EXPLAIN

## [2] 실제 연결
═══════════════════════════════

이제 실제로 MCP 서버를 연결해봅시다.

### 연결 명령어

Claude Code에서 MCP 서버를 추가하는 명령어:

```
claude mcp add [서버이름] -- [실행 명령어]
```

### 권장 서버

  ⭐⭐⭐ Notion — 가장 안정적, 문서 관리
  ⭐⭐⭐ Google Calendar — 전 직원 사용, 일정 관리
  ⭐⭐   GitHub — 엔지니어 추천, 코드 관리
  ⭐⭐   Mattermost — 채널 메시지 수집
  ⭐     ClickUp — 제품 안정성 이슈, 비권장

💡 EXEM 참고: ClickUp은 제품 자체의 안정성 이슈로
   MCP 연결을 권장하지 않습니다.
   Notion이나 Google Calendar로 실습하세요.


### 연결 예시: Notion

Notion MCP를 연결하려면:

1. Notion API 토큰이 필요합니다 (Notion → Settings → Integrations)
2. MCP 서버를 추가합니다:
```
claude mcp add notion -- npx -y @notionhq/notion-mcp-server
```
3. 연결 확인:
```
/mcp
```

### 연결 예시: Google Calendar

1. Google Calendar MCP 서버를 검색합니다
2. 인증 설정을 따릅니다
3. 서버를 추가합니다

💡 MCP 서버마다 설정 방법이 다릅니다.
   Claude에게 "Notion MCP 연결하는 법 알려줘" 같이 물어보면 도움을 줄 수 있습니다.

───────────────────────────────


## EXECUTE

### MCP 서버 연결 실습

아래 중 하나를 선택해서 연결해봅시다:

**Option A: Notion 연결**
1. Notion에서 Integration 생성 (Settings → Integrations → New)
2. 토큰을 복사
3. Claude에게 안내를 요청:
```
Notion MCP 서버를 연결하고 싶어. 단계별로 안내해줘.
```

**Option B: Google Calendar 연결**
1. Claude에게 안내를 요청:
```
Google Calendar MCP 서버를 연결하고 싶어. 단계별로 안내해줘.
```

**Option C: 다른 도구 연결**
사용하는 다른 도구가 있다면 Claude에게 물어보세요:
```
[도구 이름] MCP 서버가 있어? 있으면 연결하는 법 알려줘.
```

**연결 확인:**
```
/mcp
```
→ 추가한 서버가 목록에 보이면 성공!

**간단한 테스트:**
연결된 도구에 질문해보세요:
- Notion: "내 Notion에서 최근 문서 3개 알려줘"
- Calendar: "내 캘린더에 오늘 일정 뭐 있어?"

───────────────────────────────
