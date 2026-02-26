# Block 1: Content Digest

## EXPLAIN

### Content Digest란?

트윗, YouTube 영상, 블로그 글 등 콘텐츠를 가져와서 **소화 가능한 형태로 변환**하는 스킬입니다.

```
URL 입력
  │
  ├── 내용 추출 (자막, 텍스트, 요약)
  ├── 한국어 번역 (필요 시)
  └── Quiz-First 학습 형태로 변환
  │
  ▼
📄 소화된 콘텐츠 문서
```

### Quiz-First 학습이란?

설명을 읽기 전에 **먼저 퀴즈를 풀고**, 틀린 부분만 집중적으로 학습하는 방법입니다.

| 일반 학습 | Quiz-First 학습 |
|----------|----------------|
| 글 전체를 처음부터 읽음 | 먼저 퀴즈 5개 출제 |
| 다 읽은 후 기억나는 게 없음 | 틀린 것만 집중 학습 |
| 수동적 | 능동적 |

### EXEM에서의 활용

| 콘텐츠 | 활용 |
|--------|------|
| 기술 블로그 | 새 기술 동향 빠르게 파악 |
| YouTube 컨퍼런스 | 발표 내용 요약 + 핵심 정리 |
| 경쟁사 뉴스 | Whatap/Datadog 동향 자동 수집 |
| 내부 문서 | 긴 문서를 핵심만 추출 |

### 스킬 구조

```markdown
---
name: digest
description: URL의 콘텐츠를 소화 가능한 형태로 변환한다.
---

# Content Digest

## 실행 흐름

1. 사용자에게 URL 또는 주제를 AskUserQuestion으로 묻는다
2. WebFetch 또는 WebSearch로 콘텐츠를 가져온다
3. 핵심 내용을 추출한다
4. Quiz-First 형태로 변환한다:
   - 핵심 포인트 5개에서 퀴즈 5개 생성
   - 각 퀴즈의 정답 + 해설 포함
5. 결과를 Markdown으로 출력한다

## 출력 형식

# {제목} - 소화 노트

## 한줄 요약
{핵심을 한 문장으로}

## Quiz (먼저 풀어보세요)
1. {질문} → 정답: {답}
2. ...

## 핵심 포인트
- {포인트 1}
- {포인트 2}
...
```

## EXECUTE

Content Digest 스킬을 만들어보세요:

```
.claude/skills/에 content-digest 스킬을 만들어줘.
이름은 /digest로.

URL을 주면 내용을 가져와서 한국어로 요약하고,
Quiz-First 형태로 변환하는 스킬이야.

YouTube 영상이면 자막을 추출하고,
블로그 글이면 본문을 가져오게 해줘.
```

## QUIZ

```json
AskUserQuestion({
  "questions": [{
    "question": "Quiz-First 학습의 핵심은?",
    "header": "Quiz: Content Digest",
    "options": [
      {"label": "먼저 퀴즈로 테스트하고 모르는 것만 학습", "description": "능동적 학습"},
      {"label": "퀴즈를 많이 풀수록 좋다", "description": "양이 아니라 방식입니다"},
      {"label": "설명을 먼저 읽고 퀴즈로 확인", "description": "순서가 반대입니다"}
    ],
    "multiSelect": false
  }]
})
```

정답: 1번. **먼저 퀴즈로 테스트**하고 모르는 것만 집중 학습하는 것이 핵심입니다.
