# Claude Operating Guide

## 목적
이 저장소는 Claude Code를 내부 개발 파트너처럼 안정적으로 사용하기 위한 slim harness다.
목표는 다음 네 가지다.
- 큰 작업은 먼저 계획한다.
- 구현은 가능한 한 테스트 우선으로 진행한다.
- 중요한 맥락은 Markdown 문서로 남긴다.
- 반복 작업은 command로 표준화한다.

## 절대 규칙
- 비밀키, 토큰, `.env` 값은 출력하거나 커밋하지 않는다.
- 큰 변경은 바로 구현하지 말고 먼저 계획을 세운다.
- 완료 전에는 관련 테스트 / 린트 / 빌드 중 가능한 검증을 수행한다.
- 검증 불가 시 이유를 명확히 남긴다.
- 사용자 요청 없는 대규모 리팩터링은 금지한다.

## 기본 워크플로우
1. 요청을 이해한다.
2. 중간 이상 작업이면 `/plan` 또는 planning skill을 사용한다.
3. `docs/plans/`에 계획 문서를 남긴다.
4. 구현 시 가능하면 테스트를 먼저 작성한다.
5. 최소 구현으로 통과시킨 뒤 정리한다.
6. 필요하면 `/review`로 리뷰 문서를 만든다.
7. 마무리 시 `/ship`으로 검증 상태를 점검한다.

## 문서 위치
- 계획: `docs/plans/`
- 리뷰: `docs/reviews/`
- 설계 메모(선택): `docs/designs/`
- 활성 작업 상태(선택): `docs/active/`

## 빌드 / 테스트 명령어
프로젝트에 맞게 아래를 수정할 것.
- install: `pnpm install` 또는 `uv sync`
- test: `pnpm test` / `pytest`
- lint: `pnpm lint` / `ruff check .`
- build: `pnpm build`

## 스택 메모
이 섹션은 실제 프로젝트에 맞춰 짧게 유지한다.
예시:
- `backend/`: 백엔드 애플리케이션
- `frontend/`: Next.js App Router
- `packages/`: 공용 모듈

## 유지 원칙
- 루트 CLAUDE.md는 짧고 핵심만 유지한다.
- 스택별 세부 규칙은 skill로 분리한다.
- 폴더별 규칙이 많아지면 하위 `CLAUDE.md`를 둔다.
