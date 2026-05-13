# Phase 1 Step 1 — 남의 스킬 찾기 + 설치 (10분)

**목표**: "공개 스킬 생태계에 내 것이 있다"를 몸으로 느끼고, 데모 스킬 1개를 실제로 설치한다.

---

## EXPLAIN

### 스킬이 모여 있는 곳 3군데

1. **`npx skills search [키워드]`** — 터미널에서 바로 검색
2. **[claude.ai/skills](https://claude.ai/skills)** — 공식 웹 마켓플레이스
3. **GitHub `awesome-claude-skills`** 류 큐레이션 저장소

오늘은 **#1(터미널)**을 중심으로, 시간 되면 #2도 살짝.

### description 3초 스캔법

스킬 하나 보면 아래 3가지만 순서대로 봐요.
1. **이름** — 뭐 하는 스킬인지 힌트
2. **description 첫 문장** — 무엇을 하는가
3. **description의 트리거 키워드** — 언제 발동되는가 (따옴표 안의 말들)

**3초 안에** "이게 내게 쓸모 있나?" 판단하는 연습이 오늘의 핵심 스킬.

### 오늘의 데모 스킬 (강사가 선정)

강사가 아래 3개 중 1개를 현장에서 선택:
- `content-digest` — YouTube·PDF·트윗 요약 (감탄 포인트 큼)
- `internal-comms` — 사내 상태보고·FAQ·공지 작성
- `doc-coauthoring` — 문서 작성 단계별 가이드

---

## EXECUTE

### Step 1-1. `npx skills search` 실행

터미널에 아래 입력:
```bash
npx skills search summarize
```
(또는 본인 관심 키워드: `report`, `email`, `content` 등)

결과 화면에서 **description이 마음에 드는 스킬 3개**를 눈으로 스캔해보세요. 이름·설명·트리거만 **각 3초**씩.

### Step 1-2. 데모 스킬 설치

강사가 알려준 데모 스킬 이름을 넣어 설치:
```bash
npx skills add [강사가 알려준 이름]
```

설치 끝나면 `/help`를 입력해서 **방금 설치한 스킬 이름이 보이는지** 확인.

### Step 1-3. 한 번 호출해서 작동 확인

설치한 스킬의 트리거 키워드로 한 번 불러보세요. 예를 들어 `content-digest` 설치했다면:
```
이 YouTube 요약해줘: [아무 YouTube URL]
```

또는 강사가 제공한 **샘플 input**으로 실행.

---

```
---
👆 위 3단계를 직접 해보시고, 끝나면 "완료" 또는 "다음"이라고 입력해주세요.
```

---

## CHECK (Phase B 전용)

AskUserQuestion으로 확인:

```json
AskUserQuestion({
  "questions": [{
    "question": "데모 스킬 설치·실행 어떻게 됐어요?",
    "header": "Step 1 체크",
    "options": [
      {"label": "✅ 설치 완료 + 실행해봤어요", "description": "다음 Step(해부)으로 이동"},
      {"label": "설치는 됐는데 실행이 이상해요", "description": "트리거 키워드를 description에서 다시 찾아보기"},
      {"label": "npx 명령이 안 먹어요", "description": "claude.ai/skills 웹에서 직접 찾기로 우회"},
      {"label": "강사님 호출할게요", "description": "막힌 지점 1:1 지원 요청"}
    ],
    "multiSelect": false
  }]
})
```

### 응답별 멘트
- 완료 → "좋아요! 방금 한 일이 **4단계 사이클의 1단계 '찾기'**입니다. 이제 그 스킬을 해부해볼게요."
- 실행 이상 → description의 트리거 단어 확인 → 재시도 안내
- npx 실패 → claude.ai/skills 우회 경로 안내
- 강사 호출 → "옆에 계신 강사님께 손 들어주세요"

### 다음 Step 안내

> "Phase 1 Step 2 — **해부**로 넘어갑니다. 방금 설치한 스킬의 SKILL.md를 열어볼 거예요."
