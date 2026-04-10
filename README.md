# Claude Harness Slim Template

A low-overhead Claude Code template for internal projects with planning, TDD, review, and reusable command workflows.

목표는 단순하다.
- 큰 작업은 먼저 계획한다.
- 구현은 가능하면 TDD 흐름으로 간다.
- 중요한 맥락은 Markdown 문서로 남긴다.
- 반복 작업은 command로 표준화한다.

이 템플릿은 superpowers와 advanced-harness의 장점만 가져오고, 내부용 프로젝트에 맞게 복잡도를 줄였다.

## 포함 구성
- 짧은 루트 `.claude/CLAUDE.md`
- 재사용 가능한 skills
  - `planning`
  - `tdd-implementation`
  - `code-review`
  - `nextjs-guidelines`
- 반복 작업용 commands
  - `/plan`
  - `/review`
  - `/ship`
  - `/dev-docs`
- 문서 저장 구조
  - `docs/plans/`
  - `docs/reviews/`
  - `docs/designs/`
  - `docs/active/`

## 의도적으로 제외한 것
- 복잡한 hooks
- 다수의 agents
- MCP 다중 연결
- 특정 회사/프로젝트 전용 설정
- 과한 자동화 파이프라인

## 추천 대상
- 혼자 개발하거나 소규모 팀이 쓰는 Claude Code 템플릿
- plan 문서와 작업 기록은 남기고 싶지만 구조는 가볍게 유지하고 싶은 경우
- Next.js 프로젝트 또는 범용 웹 프로젝트 시작점이 필요한 경우

## 빠른 시작
1. 이 템플릿을 프로젝트 루트에 복사한다.
2. `.claude/CLAUDE.md` 안의 빌드/테스트 명령어를 실제 프로젝트에 맞게 수정한다.
3. 필요 없는 skill은 지우고, 필요한 skill을 추가한다.
4. 큰 작업부터 `/plan`을 사용한다.

## 권장 워크플로우
### 1) 큰 작업 시작
- `/plan`
- `docs/plans/YYYY-MM-DD-{slug}.md` 생성

### 2) 구현
- `tdd-implementation` 흐름 사용
- 가능하면 테스트 먼저 작성
- 최소 구현 → 통과 확인 → 정리

### 3) 리뷰
- `/review`
- 필요하면 `docs/reviews/YYYY-MM-DD-{slug}-review.md` 생성

### 4) 세션 종료 전 정리
- `/dev-docs`
- 현재 작업 상태를 `docs/active/`에 기록

### 5) 마무리 점검
- `/ship`
- 테스트 / 린트 / 빌드 점검

## 디렉토리 구조
```text
.claude/
  CLAUDE.md
  commands/
    dev-docs.md
    plan.md
    review.md
    ship.md
  skills/
    code-review/
      SKILL.md
    nextjs-guidelines/
      SKILL.md
    planning/
      SKILL.md
    tdd-implementation/
      SKILL.md

docs/
  active/
  designs/
  plans/
  reviews/
```

## 커스터마이징 팁
- Next.js를 안 쓰면 `nextjs-guidelines`를 삭제해도 된다.
- 백엔드 규칙이 필요하면 별도 skill을 추가하면 된다.
- 루트 `CLAUDE.md`는 짧고 핵심만 유지하는 것이 좋다.
- 세부 규칙이 많아지면 하위 폴더별 `CLAUDE.md`를 추가한다.

## 라이선스
MIT
