# PO 기여 — 요구사항에서 화면까지

이 문서는 기존 기획·구현 자료를 연결하기 위해 이번 포트폴리오 정리 과정에서 작성했다. 프로젝트 당시 원본 문서는 PRD와 MVP User Stories에서 확인한다.

## 역할과 산출물

ShinDuck은 MVP 요구사항과 유저스토리 원안을 작성하고, 대시보드 UI/UX 설계와 Streamlit 구현을 담당했다. 기획 원안의 작성자는 본인 확인에 근거한다. 팀원이 원안을 GitHub에 등록하고 팀 기준으로 정리했으므로 커밋 작성자는 원안 작성자와 다를 수 있다.

- [PRD](./prd.md): 해결할 문제, 대상 사용자, 두 가지 탐지 패턴, 포함·제외 범위, 사용자 흐름, 성공 기준
- [MVP User Stories](./mvp-user-stories.md): 4개 Epic / 11개 Feature, 사용자 요구, 수용 기준, 우선순위와 대상 Sprint
- [Sprint 1 Scope](./sprint1-scope.md): 팀이 정리한 S1 범위·완료 기준과 PO 화면 산출물
- [Demo](./demo.md): 팀 대표 시나리오를 통한 위험 이해 → 접근 경로 확인 → 조치 검토 흐름

## 요구사항과 개인 데모의 연결

| 요구사항 | 사용자 가치 | 관련 구현 | 개인 데모 범위 |
| --- | --- | --- | --- |
| F1.1 Risk Overview | 조치가 필요한 권한과 위험 분포 파악 | [Overview](../../apps/dashboard/pages/01_Overview.py) | 합성 데이터 기반 현황 표시 |
| F1.2 우선 검토 대상 | 위험한 항목부터 검토 | [Cards](../../apps/dashboard/components/cards.py) | 우선 검토 목록·요약 표현 |
| F2.1 잔존 권한 목록 | 권한·위험 등급·상태 비교 | [Asset List](../../apps/dashboard/pages/02_Asset_List.py) | 합성 사례 목록과 상태 표시 |
| F2.2 접근 경로 | 주체에서 민감 자산까지 관계 이해 | [Risk Card](../../apps/dashboard/pages/03_Risk_Card.py) | 접근 경로와 위험 요인 표현 |
| F3.1 조치 권고 | 다음 조치의 방향 파악 | [조치 패널](../../apps/dashboard/components/risk_text_panels.py) | 사전 작성된 데모 권고·placeholder |

이 표는 요구사항과 코드의 연결을 설명한다. 모든 수용 기준에 대한 실행 검증 완료를 뜻하지 않는다. 개인 데모는 실제 AI·Jira API나 자동 권한 회수를 수행하지 않는다.

## 범위 관리

S1은 F1.1/F1.2/F2.1/F2.2/F3.1을 P0로 묶어 위험 파악과 상세 근거 확인에 집중한다. 티켓 초안·수정·승인 발행은 S2, 아이덴티티 중심 매핑·이력·감사 기능은 Backlog로 구분한다. 기능의 중요도와 구현 시점을 분리해 MVP의 범위를 설명한다.

## 성공 기준

PRD의 제품 목표는 데모를 본 사람이 1분 안에 '어떤 권한이 남았는지 / 어떤 민감 자산에 닿는지 / 다음 조치가 무엇인지'를 설명할 수 있게 하는 것이다. 이는 정의된 성공 기준이며, 사용자 평가 실험을 통해 달성했다고 주장하는 수치는 아니다.

## 출처

- 기획 기준: [팀 PR #26](https://github.com/dataschool-proj2-team5/access-drift/pull/26), `be78e8bd3ce972ed7bd557cd672033611aecd697`
- 본인 대시보드 구현: [팀 PR #81](https://github.com/dataschool-proj2-team5/access-drift/pull/81), 선별 버전 `0c88146e9c5e8c7e83becb3d1d847ad91861de6c`
- PRD는 포트폴리오에서 검증하지 않은 외부 통계·요금·사건 인용을 생략했다. 나머지 제품 문서는 원본의 당시 범위와 상태를 보존했다.
