# Access Drift — 개인 기여 포트폴리오

퇴사·부서 이동·계약 종료 후 남은 접근 권한을 검토하는 보안 운영 대시보드입니다. **Microsoft Data School 팀 프로젝트에서 ShinDuck의 PO 기획 원안과 Streamlit 대시보드 구현을 정리한 개인 포트폴리오**입니다. 전체 데이터 플랫폼이나 팀원 구현을 개인 성과로 주장하지 않습니다.

## PO 기획과 요구사항

**담당: PO — MVP 요구사항·유저스토리 원안 작성, 대시보드 UI/UX 설계 및 Streamlit 구현.**

| 자료 | 확인할 내용 | 기여·출처 |
| --- | --- | --- |
| [PRD / MVP 요구사항](docs/product/prd.md) | 문제 정의, 타깃 사용자, MVP 범위, 기능·성공 기준 | ShinDuck 원안 · Pexy99 등록 |
| [MVP 유저스토리](docs/product/mvp-user-stories.md) | 4개 Epic, 11개 Feature, 수용 기준, 우선순위 | ShinDuck 원안 · Pexy99 등록 |
| [요구사항 → 화면 연결](docs/product/po-contribution.md) | F1.1~F3.1과 구현 파일 연결, 기획·구현 범위 구분 | 이번 포트폴리오 정리 문서 |
| [Sprint 1 범위](docs/product/sprint1-scope.md) | S1 필수 범위와 S2/Backlog 구분, 완료 기준 | 팀 공용 맥락 자료 |
| [MVP 데모 시나리오](docs/product/demo.md) | 대표 NHI 잔존 접근 사례와 Risk Card 흐름 | 팀 공용 맥락 자료 |

PRD와 유저스토리 원안은 ShinDuck이 작성하고 팀원이 GitHub에 등록했습니다. 원안 작성 구분은 본인 확인에 근거하며, 저장소 등록·정리 이력은 [팀 PR #26](https://github.com/dataschool-proj2-team5/access-drift/pull/26)에 남아 있습니다. 팀 합의와 후속 편집이 반영된 문서 전체를 단독 집필로 주장하지 않습니다.

## 대시보드 담당 범위와 결과

- Overview: 위험 현황과 우선 검토 대상 표시
- Asset List: 자산·신원·위험 수준·검토 상태를 비교하는 목록 화면
- Risk Card: 접근 경로, 위험 요인, 권장 조치 및 검토 정보 화면
- 화면 컴포넌트와 데이터 로딩·정규화 모듈 분리
- 24개 합성 사례와 세션 내 검토 상태 변경으로 화면 흐름 시연

기술: Python, Streamlit, pandas, Altair, Plotly, HTML/CSS. 팀 프로젝트의 플랫폼은 Azure Databricks였지만, 이 포트폴리오에는 클라우드 연결이나 배포 코드를 포함하지 않았습니다.

## 실행

```bash
cd apps/dashboard
python -m pip install -r requirements.txt
streamlit run app.py
```

별도 계정·API 키 없이 내장 합성 데이터로 동작하도록 구성했습니다. AI 응답·권장 조치·티켓 화면은 이 버전에서 데모/placeholder이며 실제 조치 API를 호출하지 않습니다. 세션 변경은 영구 저장되지 않습니다.

## 출처와 선별 기준

원본: [dataschool-proj2-team5/access-drift](https://github.com/dataschool-proj2-team5/access-drift).

기준 버전: `0c88146e9c5e8c7e83becb3d1d847ad91861de6c` — 본인 작성 대시보드 UI 정리 커밋. [PR #81](https://github.com/dataschool-proj2-team5/access-drift/pull/81)의 개별 커밋 작성자가 ShinDuck인 초기 구현을 사용했습니다. 대시보드 코드에는 이후 공동 작성·팀원 병합·실데이터 연동 변경을 포함하지 않았습니다. 제품 문서는 별도로 팀 PR #26 기준을 수록했습니다.

원본의 이미지/브랜드 자산은 가져오지 않았습니다. 이미지가 없을 때 일반 텍스트 SVG로 표시하는 포트폴리오용 보완 코드를 추가했습니다. 데모의 인명·메일 주소는 일반 예시로 치환했습니다. 팀 공용 README, 운영 문서, 인프라, CI, 원본 데이터 및 Git 이력은 제외했습니다.

## 확인 범위

선별한 Python 파일의 문법과 데이터 로딩·스키마 정합성을 확인했습니다. 이 작업 환경에서는 Streamlit 전체 UI를 실행하지 못했으므로 실제 화면의 렌더링은 별도 확인이 필요합니다. 이 저장소는 팀 시스템 전체의 실행본이 아닙니다.

Private로 준비했으며 공개 전환은 소유자의 확인 후 진행합니다.
