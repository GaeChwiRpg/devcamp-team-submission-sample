# Week 9 Team Project Evidence Checklist

Week 9는 개인 레포 미션 제출이 아니라 팀 레포 PR 기준입니다.

아래 항목이 PR에 같이 남아 있으면 가장 좋습니다.

## 필수

- 담당 기능 범위 설명
- API 계약 또는 도메인 경계 설명
- 검증 근거 1개 이상
- 팀 내 역할 명시

## 권장 증빙

- contract test 결과
- API 요청/응답 예시
- 통합 체크리스트
- 장애/병목 메모
- PR 간 의존성 정리

## 예시 문장

- "이번 PR은 재고 조회/차감 API를 담당했습니다."
- "주문 서비스와의 연동 계약은 `inventory-reserve`, `inventory-release` 두 개입니다."
- "검증은 contract test 4건과 동시 요청 시나리오 1건으로 확인했습니다."
- "남은 리스크는 캐시 invalidation과 타임아웃 처리입니다."
