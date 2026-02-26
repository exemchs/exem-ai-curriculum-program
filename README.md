# EXEM Claude Code Training

EXEM 구성원을 위한 5일 Claude Code 트레이닝 프로그램입니다.
코딩 경험이 없어도 괜찮습니다. 아래 가이드를 따라하면 됩니다.

---

## 사전 준비 (교육 담당자가 확인)

교육 시작 전, 참가자의 Anthropic 계정이 준비되어야 합니다.

| 플랜 | 비용 | 비고 |
|------|------|------|
| Claude Max | $100/월 | 권장. 교육 중 사용량 제한에 걸리지 않음 |
| Claude Pro | $20/월 | 가능하나 사용량 제한이 타이트함 |
| API Key (종량제) | 사용량 과금 | 비개발자에게 설정이 복잡하여 비권장 |

계정은 [claude.ai](https://claude.ai)에서 가입 후 구독합니다.

---

## Step 1. Git 설치 (처음 한 번만)

Git은 프로젝트를 다운로드하고, Claude Code가 내부적으로 사용하는 필수 도구입니다.

**Mac:**
1. Cursor나 터미널(아무거나)을 열고 아래를 입력합니다
2. `git --version` 입력 후 Enter
3. 설치되어 있지 않으면 "Install Command Line Developer Tools" 팝업이 뜹니다
4. **Install** 버튼 클릭 → 설치 완료까지 기다리기 (3~10분)

> 팝업이 안 뜨면 터미널에 `xcode-select --install` 입력

**Windows:**
1. [git-scm.com](https://git-scm.com)에 접속합니다
2. **Download for Windows** 클릭 → 설치 파일 실행
3. 설치 옵션은 모두 기본값으로 **Next** 클릭하면 됩니다

## Step 2. Node.js 설치 (처음 한 번만)

Claude Code 자체는 Node.js 없이 동작하지만, Day 2에서 외부 도구(Notion, Mattermost 등)를 연결할 때 필요합니다.

1. [nodejs.org](https://nodejs.org)에 접속합니다
2. **LTS** (초록색 버튼)를 클릭해서 다운로드합니다
3. 다운로드된 파일을 실행해서 설치합니다 (기본값으로 Next)

> 설치 확인: 터미널에 `node --version` 입력 → `v22.x.x` 같은 버전이 나오면 성공

## Step 3. Cursor 에디터 설치

Cursor는 파일을 보면서 작업할 수 있는 에디터입니다. 코드를 몰라도 파일 탐색기처럼 사용하면 됩니다.

1. [cursor.com](https://cursor.com)에 접속합니다
2. **Download** 버튼을 클릭합니다
3. 다운로드된 파일을 실행해서 설치합니다
4. 설치가 끝나면 Cursor를 실행합니다

> Mac에서 "개발자를 확인할 수 없습니다" 경고가 나오면:
> **시스템 설정 → 개인 정보 보호 및 보안 → 아래로 스크롤 → "확인 없이 열기" 클릭**

## Step 4. 터미널 열기

Cursor를 실행한 뒤, 터미널을 엽니다. Claude Code는 이 터미널에서 동작합니다.

```
Cursor 상단 메뉴 → Terminal → New Terminal
```

아래쪽에 검은 창이 나타나면 성공입니다. 이것이 **터미널**입니다.

> 단축키: Mac `Ctrl + 백틱(`)` / Windows `` Ctrl + ` ``

## Step 5. Claude Code 설치

터미널에 아래 명령어를 **복사해서 붙여넣고** Enter를 누르세요.

**Mac / Linux:**
```bash
curl -fsSL https://claude.ai/install.sh | bash
```

**Windows (PowerShell):**

PowerShell 실행 정책 때문에 명령이 안 될 수 있습니다. 아래 두 줄을 순서대로 실행하세요.

```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
irm https://claude.ai/install.ps1 | iex
```

설치가 끝나면 **터미널을 껐다 다시 열어주세요** (PATH가 반영되어야 `claude` 명령이 인식됩니다).

> 설치 확인: 터미널에 `claude --version` 입력 → 버전이 나오면 성공

## Step 6. 프로젝트 클론

터미널에 아래 명령어를 붙여넣고 Enter를 누르세요.

```bash
git clone https://github.com/exemchs/exem-ai-curriculum-program.git
```

## Step 7. 프로젝트 폴더 열기

Cursor에서 방금 클론한 폴더를 엽니다.

```
Cursor 상단 메뉴 → File → Open Folder → exem-ai-curriculum-program 선택
```

폴더를 열면 왼쪽에 파일 목록이 보입니다. CLAUDE.md, README.md가 보이면 성공입니다.

## Step 8. Claude Code 실행

터미널을 새로 열고 (`Terminal → New Terminal`), `claude`를 입력합니다.

```bash
claude
```

처음 실행하면 브라우저가 열리면서 Anthropic 계정 로그인을 안내합니다. 로그인하면 준비 완료.

## Step 9. 트레이닝 시작

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
| `claude` 명령이 안 됨 | 터미널을 껐다 다시 열기. 그래도 안 되면 Claude Code 재설치 |
| `git` 명령이 안 됨 | Mac: `xcode-select --install` / Windows: git-scm.com에서 설치 |
| Mac 보안 경고 ("개발자 확인 불가") | 시스템 설정 → 개인 정보 보호 및 보안 → "확인 없이 열기" |
| Windows PowerShell 스크립트 차단 | `Set-ExecutionPolicy RemoteSigned -Scope CurrentUser` 실행 |
| 로그인 후 "사용 불가" | Anthropic 구독 플랜(Pro/Max) 활성화 여부 확인 |
| `npx` 명령이 안 됨 (Day 2) | Node.js 미설치. nodejs.org에서 LTS 설치 |

## 문의

문제가 발생하면 조현서(CX그룹)에게 연락하세요.
