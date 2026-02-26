# EXEM Claude Code Training

EXEM 구성원을 위한 5일 Claude Code 트레이닝 프로그램입니다.
코딩 경험이 없어도 괜찮습니다. 아래 가이드를 따라하면 됩니다.

---

## Step 1. Cursor 에디터 설치

Cursor는 파일을 보면서 작업할 수 있는 에디터입니다. 코드를 몰라도 파일 탐색기처럼 사용하면 됩니다.

1. [cursor.com](https://cursor.com)에 접속합니다
2. **Download** 버튼을 클릭합니다
3. 다운로드된 파일을 실행해서 설치합니다
4. 설치가 끝나면 Cursor를 실행합니다

## Step 2. 터미널 열기

Cursor를 실행한 뒤, 터미널을 엽니다. Claude Code는 이 터미널에서 동작합니다.

```
Cursor 상단 메뉴 → Terminal → New Terminal
```

아래쪽에 검은 창이 나타나면 성공입니다. 이것이 **터미널**입니다.

> 단축키: Mac `Ctrl + 백틱(`)` / Windows `Ctrl + 백틱(\`)`

## Step 3. Claude Code 설치

터미널에 아래 명령어를 **복사해서 붙여넣고** Enter를 누르세요.

**Mac / Linux:**
```bash
curl -fsSL https://claude.ai/install.sh | bash
```

**Windows (PowerShell):**
```powershell
irm https://claude.ai/install.ps1 | iex
```

설치가 끝나면 터미널을 한 번 껐다 다시 열어주세요.

> 문제가 생기면? 터미널에 `claude --version`을 입력해보세요. 버전이 나오면 설치 완료.

## Step 4. 프로젝트 클론

터미널에 아래 명령어를 붙여넣고 Enter를 누르세요.

```bash
git clone https://github.com/exemchs/exem-ai-curriculum-program.git
```

> **git이 설치 안 되어 있다면?**
> - Mac: 터미널에 `xcode-select --install` 입력 후 설치
> - Windows: [git-scm.com](https://git-scm.com) 에서 다운로드 후 설치

## Step 5. 프로젝트 폴더 열기

Cursor에서 방금 클론한 폴더를 엽니다.

```
Cursor 상단 메뉴 → File → Open Folder → exem-ai-curriculum-program 선택
```

폴더를 열면 왼쪽에 파일 목록이 보입니다. CLAUDE.md, README.md가 보이면 성공입니다.

## Step 6. Claude Code 실행

터미널을 새로 열고 (`Terminal → New Terminal`), `claude`를 입력합니다.

```bash
claude
```

처음 실행하면 Anthropic 계정 로그인을 안내합니다. 로그인하면 준비 완료.

> **Anthropic 계정이 없다면?** [console.anthropic.com](https://console.anthropic.com)에서 먼저 가입하세요.

## Step 7. 트레이닝 시작

Claude Code가 실행되면, 아래를 입력해서 1일차를 시작합니다.

```
/day1-start
```

---

## 커리큘럼

| Day | 명령어 | 주제 | 배우는 것 | 만드는 것 |
|-----|--------|------|-----------|-----------|
| 1 | `/day1-start` | 시작하기 | Claude Code 설치, CLAUDE.md, 핵심 기능 | CLAUDE.md 규칙서 |
| 2 | `/day2-connect` | 외부 도구 연결 | MCP 개념, 서버 연결 | Context Sync 스킬 뼈대 |
| 3 | `/day3-skill` | 나만의 스킬 완성 | Subagent, 출력 포맷, 검증 | 완성된 스킬 1개 |
| 4 | `/day4-apply` | 실무 적용 | Multi-agent, Quiz-First 학습 | Session Wrap + Content Digest |
| 5 | `/day5-graduate` | 졸업 | 종합 프로젝트 | 졸업 프로젝트 스킬 |

## 트러블슈팅

| 문제 | 해결 |
|------|------|
| `claude` 명령이 안 됨 | 터미널을 껐다 다시 열기 |
| 권한 에러 (Mac) | 터미널을 관리자 권한으로 재실행 |
| `git` 명령이 안 됨 | Mac: `xcode-select --install` / Windows: git-scm.com에서 설치 |
| 로그인이 안 됨 | console.anthropic.com에서 계정 확인 |

## 문의

문제가 발생하면 조현서(CX그룹)에게 연락하세요.
