# 🧠 AIQ INPUT REQUIRED

<!-- [2026-07-01] Dry-run hardening: URL-only page now starts with the exact fallback output as content, not an instruction wrapper. -->

# 🧠 AIQ INPUT REQUIRED

**Template: AIQ-NEED-INPUT-v2**
**Status: 평가 보류**
**Reason:** 평가 대상과 근거가 아직 제공되지 않았습니다.

## 필요한 입력

**평가 대상**
- 입력 예시: 특정 AI 사용 사례, 대화 로그, 업무 흐름, 산출물

**목적**
- 입력 예시: 무엇을 끝내려던 작업인지

**산출물**
- 입력 예시: 답변, 문서, 코드, 회의록, 자동화 결과, 배포물

**근거**
- 입력 예시: 원문, 로그, 테스트, 계산, 링크, 스크린샷, 사용 기록

**제약**
- 입력 예시: 사용자 개입, 보안/승인 경계, 실패/재작업 여부

## 붙여넣기용 요청

아래 AI 사용 사례를 AIQ-REPORT-v2 템플릿으로 평가해줘.
목적: ...
사용한 AI/도구: ...
산출물: ...
근거/로그/링크: ...
사용자가 다시 고친 부분: ...
안전/승인 경계: ...

---

# AIQ-REPORT-v2 scoring spec

Use `AIQ-REPORT-v2` only when a concrete target and evidence are provided.

Evaluation loop:

```text
목적 이해 → 맥락 연결 → 작업 설계 → 실행 → 검증 → 판단 → 학습/재사용 → 안전한 위임
```

Raw Score axes:
- 의도 파악·목적 이해 (15)
- 맥락 연결 (15)
- 작업 설계 (10)
- 실행력 (15)
- 검증력 (15)
- 판단·우선순위 (10)
- 학습·재사용 (10)
- 안전·위임 경계 (10)

Evidence Multiplier:
- E0 자기진술 ×0.70
- E1 산출물 있음 ×0.85
- E2 사용 흔적 있음 ×0.95
- E3 검증 있음 ×1.00
- E4 반복 운영 증거 있음 ×1.05

User Burden Penalty: -3 each, max -15.

Adjusted AIQ = (Raw Score × Evidence Multiplier) - User Burden Penalty.

Levels: L0 검색형, L1 생성형, L2 보조자형, L3 실행형, L4 검증형, L5 운영형.

```markdown
# 🧠 AIQ REPORT

## 🏁 종합 판정

**Template: AIQ-REPORT-v2**
**Target:** ...
**Adjusted AIQ:** 00 / 100
**Raw Score:** 00 / 100
**Evidence Level:** E0~E4 (×0.00)
**User Burden Penalty:** -0
**Level:** L0~L5 / 판정명
**한 줄 판정:** “...”

## ✅ Gate Checklist

- 목적 명확성: Yes/Revise/No — 근거: ...
- 산출물 존재: Yes/Revise/No — 근거: ...
- 맥락 사용: Yes/Revise/No — 근거: ...
- 실행 경로: Yes/Revise/No — 근거: ...
- 검증 경로: Yes/Revise/No — 근거: ...
- 안전 경계: Yes/Revise/No — 근거: ...
- 재사용 가능성: Yes/Revise/No — 근거: ...

## 📊 점수표

- 의도 파악·목적 이해 (15): 00 — 근거: ...
- 맥락 연결 (15): 00 — 근거: ...
- 작업 설계 (10): 00 — 근거: ...
- 실행력 (15): 00 — 근거: ...
- 검증력 (15): 00 — 근거: ...
- 판단·우선순위 (10): 00 — 근거: ...
- 학습·재사용 (10): 00 — 근거: ...
- 안전·위임 경계 (10): 00 — 근거: ...

## 🔎 확인됨 / 확인 못 함

### 확인됨
- ...

### 확인 못 함
- ...

### 추정
- ...

## 💪 강점 TOP 3

1. ...
2. ...
3. ...

## 🧩 개선 TOP 3

1. ...
2. ...
3. ...

## 🛠 업그레이드 처방

1. 처방: ... / 기대 효과: ...
2. 처방: ... / 기대 효과: ...
3. 처방: ... / 기대 효과: ...

## 🧾 공유용 한 줄 카드

> 내 AIQ는 **00 / 100, L0~L5**
> 한 줄: “...”
```
