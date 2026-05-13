# Phase 2 Step 1 — 내 스킬 제작 (15분)

**목표**: Phase 1에서 본 구조를 모방해 **본인 업무 스킬 1개**를 완성. 월요일에 쓸 수 있는 수준.

**AskUserQuestion 허용**: 사전 준비물 수집용 AQ 자유롭게 사용.

---

## EXPLAIN

### Phase 1에서 본 것 그대로 적용

방금 가공한 `my-[스킬이름]`의 구조 기억나시죠?
```
--- frontmatter ---
name + description
--- body ---
Step 1, Step 2, Step 3
제약 사항
```

이걸 **내 업무**로 바꾸면 Phase 2 Step 1 완성. 새로 배울 건 없어요.

### 재료는 사전 준비물 3종 세트

1. **업무 이름** (예: "매주 월요일 JD 검토")
2. **Input 예시 1개** (실제 JD 텍스트)
3. **Output 예시 1개** (실제 검토 결과물)

이 3가지가 있으면 스킬은 10분 안에 나옵니다. 없으면 강사에게 백업 시나리오 카드 요청.

---

## EXECUTE

### Step 1-1. 3종 세트 꺼내기 (1분, AQ)

```json
AskUserQuestion({
  "questions": [{
    "question": "오늘 만들 스킬의 업무 이름을 알려주세요",
    "header": "업무 이름",
    "options": [
      {"label": "주간보고 작성", "description": "주 1회 팀 주간보고"},
      {"label": "JD 검토·수정", "description": "직무 기술서 리뷰"},
      {"label": "회의 후 액션아이템 정리", "description": "미팅 메모 → 할 일 목록"},
      {"label": "고객/후보자 회신 초안", "description": "받은 메일에 답장 초안"}
    ],
    "multiSelect": false
  }]
})
```

위 중 하나 선택하거나, "Other"로 본인 업무 자유 입력.

### Step 1-2. frontmatter 작성 (4분)

Claude에게 요청:

```
"[방금 선택한 업무 이름]" 스킬의 frontmatter를 만들어줘.
동료가 이 작업이 필요할 때 나에게 할 만한 말 3~5가지를 
트리거 키워드로 넣어서 description 3가지 버전을 제안해줘.
```

Claude가 3가지 제시 → 1개 선택.

**선택 기준**:
- 내 말투가 들어있는가
- 명사 3~5개가 들어있는가 (업무 관련 단어)
- 한 문장이 80자 이내인가

### Step 1-3. Input/Output 쌍 보여주기 (5분)

Claude에게:

```
내가 Input과 Output 예시를 보여줄게.
이 패턴대로 작동하는 body를 작성해줘.

[INPUT]
(실제 본인 Input 예시 붙여넣기)

[OUTPUT]
(실제 본인 Output 예시 붙여넣기)
```

Claude가:
1. Input/Output 쌍 분석
2. Step 1~3 구조로 body 초안 생성
3. 제약 사항(분량·문체 등) 추출

### Step 1-4. 파일 저장 + 실행 검증 (5분)

Claude에게:

```
지금까지 만든 frontmatter + body를 합쳐서
C:\Users\admin\.claude\skills\my-[업무영문이름]\SKILL.md 로 저장해줘.
```

저장 후 **다른 Input**으로 실행:

```
my-[업무이름] 스킬로 이것 처리해줘:
[새로운 Input]
```

결과 비교:
- 80% 이상 기대한 Output 나오면 → ✅ 완성
- 안 맞으면 → "body에 [XX] 추가해줘" 식으로 1~2번 튜닝

---

```
---
👆 본인 스킬이 작동하는 걸 확인하셨으면 "완료"를 입력해주세요.
```

---

## CHECK (Phase B)

```json
AskUserQuestion({
  "questions": [{
    "question": "방금 만든 스킬, 월요일 출근해서 쓸 수 있을 것 같아요?",
    "header": "Phase 2-1 체크",
    "options": [
      {"label": "✅ 바로 쓸 수 있어요", "description": "오늘 최고의 성공 🎉 → Slack 공유로 이동"},
      {"label": "거의 다 됐어요", "description": "D+7 클리닉에서 마무리 가능 → Slack 공유로 이동"},
      {"label": "방향은 잡혔지만 더 다듬어야 해요", "description": "공유는 v0.1로 올려두고 나중에 업데이트"},
      {"label": "막혔어요", "description": "강사 1:1 요청"}
    ],
    "multiSelect": false
  }]
})
```

### 응답별 멘트

- 바로 쓸 수 있어요 → "월요일에 꼭 한 번 실행해 보세요. **한 번 쓴 스킬은 또 쓰게 됩니다**."
- 거의 다 됐어요 → "충분합니다. 공유하시고 D+7 클리닉에서 마무리해요."
- 방향만 → "v0.1로 공유하는 게 맞아요. 피드백 받아서 v0.2 만들면 됨."
- 막혔어요 → 강사 호출 안내

### 다음 Step

> "마지막 — **Slack 공유**로 4단계 사이클을 완주합니다."
