# Week 9 Team Project — Evidence Checklist

Week 9는 개인 레포 미션 제출이 아니라 팀 레포 PR 기준입니다. PR마다 + 팀 단위로 남겨야 할 자산을 단계별로 정리.

## 개인 PR마다 (최소)

- [ ] 담당 기능 범위 설명
- [ ] **본 PR이 다룬 라이프사이클 단계 명시** (코딩 / 테스트 / 리뷰 / 운영 중 어디)
- [ ] API 계약 또는 도메인 경계 설명
- [ ] 검증 근거 1개 이상 (contract test, E2E, 측정 결과 중)
- [ ] 팀 내 역할 명시

## 권장 증빙 (PR 본문 또는 evidence 폴더)

- contract test 결과 또는 단위 테스트 통과 로그
- API 요청/응답 예시
- E2E 시나리오 결과 (Playwright/Browser MCP)
- 통합 체크리스트
- 장애/병목 메모
- PR 간 의존성 정리

## 팀 단위 산출물 (라이프사이클 5 단계 모두)

### 1. 기획 단계 (책 9주차 03)

- [ ] `PRD.md` — Product Requirements Document
- [ ] Jira (또는 GitHub Issues) 티켓 분해 + AI 협업 흔적 (Jira MCP 사용 시)
- [ ] 페르소나 / 성공 지표 / 제약 사항 명시

### 2. 코딩 단계 (책 7주차 04~07, 9주차 02·04·05)

- [ ] `CLAUDE.md` — 팀 헌법 (도메인 + 코딩 규칙 + 작업 경계)
- [ ] `API-CONTRACT.md` + 변경 이력
- [ ] `.claude/commands/` 또는 `.claude/hooks/` 1개 이상 (선택)
- [ ] gh CLI 또는 Sub-agents 사용 흔적 (선택)

### 3. 테스트 단계 (책 9주차 06)

- [ ] `tests/e2e/` Playwright MCP 시나리오 ≥ 1
- [ ] 또는 contract test 통과 로그
- [ ] 테스트 시나리오 선택 근거 (왜 이 흐름을 자동화 우선했는지)

### 4. 리뷰 단계 (책 10주차 01)

- [ ] `.github/workflows/ai-review.yml` (Claude GitHub Actions) 또는 CodeRabbit 설정
- [ ] AI 리뷰가 잡은 사례 1건 + 팀이 수정한 흔적
- [ ] AI vs 팀원 리뷰 비교 메모 (각자 무엇이 강한지)

### 5. 배포·운영 단계 (책 10주차 06, 02~05)

- [ ] `MONITORING.md` — Sentry MCP 또는 모니터링 도구 설정
- [ ] Docker Compose 또는 IaC (Terraform) 중 1개 이상
- [ ] 운영 단계에서 AI에게 위임한 작업 1건 (예: Sentry 에러 분석)

### 6. 통합 / 문서화

- [ ] `INTEGRATION-LOG.md` — 팀 통합 진행 (일자별 + 담당자별)
- [ ] `LIFECYCLE-COVERAGE.md` — 5 단계 누가 무엇을 적용했는지 매트릭스

## AI 보조 기능 검증 (공통 필수)

- [ ] AI 보조 기능 1개 이상 구현 (요약/분류/우선순위 추천 등)
- [ ] AI 결과 검증 메모 (정확도 어떻게 측정, 사람 최종 판단 기준)
- [ ] hallucination 사례 1건 + 잡은 방법

## 예시 문장

- "이번 PR은 재고 조회/차감 API를 담당했습니다 (코딩 + 테스트 단계)."
- "주문 서비스와의 연동 계약은 `inventory-reserve`, `inventory-release` 두 개입니다."
- "검증은 contract test 4건과 Playwright E2E 1건, 동시 요청 50건 시나리오로 확인했습니다."
- "리뷰 단계는 .github/workflows/ai-review.yml이 처리하고, 팀원 B가 운영 단계 Sentry MCP를 담당합니다."
- "남은 리스크는 캐시 invalidation과 타임아웃 처리입니다."
