# Week 9 Team Project — PR 본문 sample

> 팀 프로젝트 개인 PR 1개의 본문이 어떤 형식이어야 하는지 보여주는 sample. 라이프사이클 단계 명시가 핵심.

---

## Team Project Metadata

- team: cohort1-team-A
- domain: 운영 티켓 시스템 (추천 프로젝트 1번)
- domain_owner: inventory-api  (본 PR 담당 영역)
- lifecycle_stage: 코딩 + 테스트  (본 PR이 다룬 단계)
- verification_scope: contract-test, e2e-playwright

## What Changed

- 재고 조회/차감 API 계약을 팀 기준으로 정리.
- 담당 영역 코드 1건 + Playwright E2E 시나리오 1건을 같이 추가.
- @Lock(PESSIMISTIC_WRITE) 적용 + 동시 50 요청 시나리오 검증.

## Lifecycle Stages 적용

| 단계 | 본 PR 기여 |
| --- | --- |
| 기획 | (해당 없음 — Jira 티켓 INV-12, INV-13 처리) |
| 코딩 | InventoryService.decrease + InventoryRepository.findByIdForUpdate 추가 |
| 테스트 | tests/e2e/inventory-decrease.spec.ts (Playwright) — 동시 요청 50건 검증 |
| 리뷰 | (PR 머지 전 .github/workflows/ai-review.yml가 자동 트리거) |
| 운영 | (해당 없음) |

## Evidence

- API 계약 변경: `API-CONTRACT.md` Inventory v0.3 (POST /api/inventory/{id}/decrease)
- Contract test: `src/test/java/.../InventoryContractTest.java` 4개 통과
- E2E test: `tests/e2e/inventory-decrease.spec.ts` Playwright 50 동시 요청 결과
- 담당 기능 데모 로그: `INTEGRATION-LOG.md`의 Day 3 항목

## Team Notes

- 내 역할: 코딩 단계 (재고 동시성) + 테스트 단계 (E2E 시나리오)
- 팀 내 연동 포인트:
  - 주문 서비스 (담당: 팀원 B)
  - Redis 캐시 레이어 (담당: 팀원 D)
- 남은 리스크:
  - 락 전략 비교 (현재 pessimistic만, optimistic 부하 테스트 후속)
  - 운영 단계 모니터링은 별도 PR로 분리 예정

## 검증 루프 4단계 (Week 8 정착)

- [ ] prompt 작성 시 페·목·형·제 4 요소 강제
- [x] AI 응답 직후 claude.md 검증 규칙 적용
- [x] 도구 호출 시 PreToolUse hook
- [x] PR 머지 전 본인이 직접 실측

## 참고

- 역할 분담: [week9-team-role-split.md](./week9-team-role-split.md)
- evidence 체크리스트: [week9-team-project-evidence-checklist.md](./week9-team-project-evidence-checklist.md)
- 5 단계 적용 흔적: [week9-team-lifecycle-coverage.md](./week9-team-lifecycle-coverage.md)
