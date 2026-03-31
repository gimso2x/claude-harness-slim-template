---
name: code-review
description: 현재 변경사항을 근거 중심으로 리뷰하고 필요하면 docs/reviews 아래에 Markdown 리뷰 문서를 남기는 스킬. 트리거 예시: 리뷰해줘, 코드리뷰해줘, 변경사항 점검해줘
---

# Code Review Skill

## 목적
변경사항을 취향이 아니라 근거 중심으로 검토한다.

## 우선순위
- P1: 반드시 수정 필요
- P2: 수정 강력 권장
- P3: 개선 권장
- P4: 사소한 제안

## 리뷰 기준
- 요구사항 충족 여부
- 버그 가능성 / 경계 조건
- 예외 처리
- 테스트 충분성
- 유지보수성

## 절차
1. 변경 목적과 범위를 확인한다.
2. 변경 파일과 관련 테스트를 본다.
3. 빠진 요구사항이 없는지 본다.
4. 리스크가 큰 로직을 점검한다.
5. 필요시 `docs/reviews/YYYY-MM-DD-{slug}-review.md` 작성

## 템플릿
```md
# Code Review - {작업명}

- 날짜: YYYY-MM-DD
- 상태: draft | shared | resolved

## Summary

## Findings

### P1 - {파일}:{위치}
- 근거:
- 문제:
- 제안:
- side effect:
```
