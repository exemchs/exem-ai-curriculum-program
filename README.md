# EXEM Claude Code Training

EXEM 구성원을 위한 Claude Code 트레이닝 프로그램입니다.
코딩 경험이 없어도 괜찮습니다. 아래 가이드를 따라하면 됩니다.

---

## 사전 준비

시작 전, 3가지를 준비해 주세요.

### 1. Git

**Mac:**

터미널에 `git` 입력 → "개발자 도구 설치" 팝업이 뜨면 설치 클릭.
버전 번호가 바로 나오면 이미 설치된 상태입니다.

> 터미널 여는 법: `⌘ Space` → "터미널" 검색 → Enter

**Windows:**

[git-scm.com/downloads/win](https://git-scm.com/downloads/win) → 주황색 **Click here to download** 클릭.
설치 시 모든 옵션 **Next** 클릭 (기본값 유지).

### 2. Node.js

**Mac:**

[nodejs.org/ko/download](https://nodejs.org/ko/download) → 페이지 하단 스크롤 → 초록색 **macOS 설치 프로그램 (.pkg)** 버튼 클릭.

**Windows:**

[nodejs.org/ko/download](https://nodejs.org/ko/download) → 페이지 하단 스크롤 → 초록색 **Windows 설치 프로그램 (.msi)** 버튼 클릭.

> 설치 확인: 터미널에 `node --version` 입력 → `v22.x.x` 같은 버전이 나오면 성공

### 3. Claude 계정

[claude.ai](https://claude.ai)에서 가입 후 **Pro ($20/월)** 이상 구독 필요.
무료 플랜으로는 Claude Code를 사용할 수 없습니다.

| 플랜 | 비용 | 비고 |
|------|------|------|
| Claude Max | $100/월 | 권장. 교육 중 사용량 제한에 걸리지 않음 |
| Claude Pro | $20/월 | 가능하나 사용량 제한이 타이트함 |
| Teams / Enterprise | 기업별 | SSO 지원, 관리자 설정 필요 |

### 시스템 요구사항

| 항목 | 최소 요구 |
|------|----------|
| macOS | 13.0 (Ventura) 이상 |
| Windows | 10 (1809) 이상 |
| RAM | 4GB 이상 |
| 네트워크 | 인터넷 연결 필수 |

---

## 시작하기

사전 준비가 끝났으면, 5단계로 시작합니다.

### Step 1. Cursor 설치

Cursor는 파일을 보면서 작업할 수 있는 에디터입니다. 코드를 몰라도 파일 탐색기처럼 사용하면 됩니다.

- [cursor.com/downloads](https://www.cursor.com/downloads)에서 다운로드 → 설치 → 실행

> Mac에서 "개발자를 확인할 수 없습니다" 경고가 나오면:
> **시스템 설정 → 개인 정보 보호 및 보안 → 아래로 스크롤 → "확인 없이 열기" 클릭**

### Step 2. 터미널 열기

Cursor 안에 내장된 터미널을 열어주세요. Claude Code는 이 터미널에서 동작합니다.

**Mac:** 화면 최상단 메뉴바 → **Terminal** → **New Terminal**

**Windows:** Cursor 창 상단 메뉴바 → **Terminal** → **New Terminal**

아래쪽에 검은 창이 나타나면 성공입니다.

### Step 3. Claude Code 설치

터미널에 아래 명령어를 붙여넣고 Enter를 누르세요.

```bash
npm install -g @anthropic-ai/claude-code
```

설치가 끝나면 **터미널을 껐다 다시 열어주세요** (PATH가 반영되어야 `claude` 명령이 인식됩니다).

> 설치 확인: 터미널에 `claude --version` 입력 → 버전이 나오면 성공

### Step 4. Claude 로그인

터미널에 `claude`를 입력하면 로그인 화면이 나타납니다.

```bash
claude
```

**Login with Anthropic** 선택 → 브라우저에서 로그인 완료.

### Step 5. 한줄로 시작

터미널에 아래 명령어를 붙여넣으면 프로젝트 다운로드 + Claude 실행까지 한 번에 됩니다.

```bash
git clone https://github.com/exemchs/exem-ai-curriculum-program.git && cd exem-ai-curriculum-program && claude
```

> 파일 목록을 눈으로 보고 싶다면: Cursor 메뉴 **File → Open Folder** → exem-ai-curriculum-program 선택

---

## 커리큘럼

| Day | 주제 | 내용 | 시간 |
|-----|------|------|------|
| 0 | 오리엔테이션 | Cursor 둘러보기, Claude와 첫 대화, 멈추기/이어하기 | ~5분 |
| 1 | AI에게 잘 시키는 법 | 컨텍스트 엔지니어링, CO-STAR, CRIT Interview, CLAUDE.md | ~1시간 |
| 2 | 내 업무를 AI로 해보기 | 위임 프레임워크(Just Me/Delegate/Automate), AI 신뢰도 | ~1시간 |
| 3 | 도구 연결하기 | MCP 개념, Notion·Calendar 연결 실습, 도구 활용 | ~1시간 |
| 4 | 자동화하기 | Skill 제작, 검증 루프 설계, 반복 가능한 워크플로우 | ~1시간 |
| 5 | 졸업 | 5일간 정리, 졸업 프로젝트 완성, 팀 공유 | ~1시간 |

Day 0은 프로젝트를 열면 자동으로 시작됩니다.
Day 1부터는 Claude에게 `/day1` 같은 명령어를 입력하면 됩니다.

| Day | 명령어 |
|-----|--------|
| 1 | `/day1` |
| 2 | `/day2` |
| 3 | `/day3` |
| 4 | `/day4` |
| 5 | `/day5` |

---

## 멈출 때

잠시 쉬고 싶을 때, 터미널에 한마디만 입력하세요.
Claude가 진행 상황을 저장합니다. 이후 터미널을 닫아도 됩니다.

```
> 여기까지 정리해줘
```

## 이어할 때

다시 시작하고 싶을 때, 3단계면 됩니다.

1. Cursor 열기 → **Terminal** → **New Terminal**
2. 터미널에 입력:
   ```bash
   cd exem-ai-curriculum-program && claude
   ```
   > `cd`는 "이 폴더로 이동해"라는 뜻입니다. 폴더를 다른 위치에 저장했다면 `cd` 뒤의 경로를 그 위치로 바꿔주세요.
3. Claude에게 입력:
   ```
   > 이어서 해줘
   ```

---

## 트러블슈팅

| 문제 | 해결 |
|------|------|
| `claude` 명령이 안 됨 | 터미널을 껐다 다시 열기. 그래도 안 되면 `npm install -g @anthropic-ai/claude-code` 재실행 |
| `npm` 명령이 안 됨 | Node.js 미설치. [nodejs.org/ko/download](https://nodejs.org/ko/download)에서 설치 |
| `git` 명령이 안 됨 (Mac) | 터미널에 `git` 입력 → "개발자 도구 설치" 팝업에서 설치 클릭 |
| `git` 명령이 안 됨 (Windows) | [git-scm.com/downloads/win](https://git-scm.com/downloads/win)에서 Git for Windows 설치 |
| Mac 보안 경고 ("개발자 확인 불가") | 시스템 설정 → 개인 정보 보호 및 보안 → "확인 없이 열기" |
| 로그인 후 사용 불가 | 무료 플랜은 Claude Code 지원 안 됨. Pro/Max 구독 필요 |
| Windows에서 Git Bash 못 찾는 오류 | settings.json에 `CLAUDE_CODE_GIT_BASH_PATH` 설정 ([공식 문서](https://code.claude.com/docs/en/setup) 참고) |

---

## 알아두면 좋은 것들

**이 프로그램은 왜 만들었나요?**
Claude Code가 어렵게만 느껴지는 비전공자를 위해 난이도를 낮춰 구성했습니다.

**커리큘럼은 어떻게 만들어졌나요?**
Claude Code 교육 오픈소스를 참조하여 EXEM 업무 환경에 맞게 재구성했습니다.

**오류를 발견하면?**
조현서 그룹장에게 보고해 주세요.

**더 많은 팁이 필요하다면**
BX팀 박승훈 대리님의 블로그에서 실무 팁을 확인하세요 → [blog.huns.site](https://blog.huns.site/blog/posts/ai/claude)

---

## 참고

- [Claude Code 공식 문서](https://code.claude.com/docs/ko)
- [Claude Code 설치 가이드](https://code.claude.com/docs/en/setup)
- [Claude Code 터미널 가이드](https://code.claude.com/docs/en/terminal-guide) (터미널이 처음인 분)
