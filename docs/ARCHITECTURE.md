# Architecture

> Status: Directional. Framework and backend are intentionally undecided.

## Core principle

**Content model first, framework second.**

놀히스토리의 핵심 자산은 화면 코드가 아니라 구조화된 역사 콘텐츠와 그 관계입니다.

## Layer boundaries

권장 개념 구조:

```text
content/data
    ↓
domain model + validation
    ↓
application/use cases
    ↓
UI components
    ↓
browser/platform adapters
```

UI 컴포넌트 내부에 역사 사실 데이터, 출처, 관계 정보를 대량으로 하드코딩하지 않습니다.

## Content/data

콘텐츠는 가능한 한 다음 특성을 갖도록 설계합니다.

- 구조화된 데이터
- 안정적인 ID
- 출처 메타데이터
- 관계 표현 가능
- UI 문구와 원자료 메타데이터 분리
- 스키마 검증 가능

## State

- URL로 표현할 가치가 있는 탐색 상태는 URL 상태를 우선 검토합니다.
- 단기 UI 상태와 영속 데이터를 구분합니다.
- 같은 의미의 상태를 여러 저장소에 중복 보관하지 않습니다.

## Persistence

도입 순서 원칙:

1. 정적 데이터
2. 브라우저 로컬 저장
3. 파일/정적 콘텐츠 배포
4. 서버/API/DB

앞 단계로 해결할 수 없는 요구가 확인될 때 다음 단계로 이동합니다.

## Backend trigger conditions

다음과 같은 요구가 실제로 생기면 백엔드를 검토합니다.

- 여러 기기 사이 사용자 데이터 동기화
- 공개 공유 콘텐츠의 중앙 저장
- 교사-학생 계정 관계
- 실시간 협업
- 서버에서만 안전하게 보관해야 하는 비밀키
- 운영자가 중앙에서 콘텐츠를 즉시 갱신해야 하는 경우

## Dependency policy

라이브러리는 다음 경우에만 추가합니다.

- 브라우저 표준 API로 구현하면 복잡도/오류 위험이 더 큰 경우
- 지속적으로 유지보수되는 라이브러리인 경우
- 번들 크기와 접근성에 미치는 영향이 수용 가능한 경우

작은 유틸리티 하나를 위해 큰 프레임워크를 추가하지 않습니다.

## Testing strategy

기술 스택 확정 후 최소 다음 층을 둡니다.

- schema/data validation
- domain logic unit tests
- critical interaction tests
- one end-to-end happy path

역사 콘텐츠 정확성은 코드 테스트만으로 충분하지 않으므로 별도의 콘텐츠 리뷰 절차를 유지합니다.

## Architecture decisions

중요한 기술 선택은 이 문서 아래에 날짜와 함께 짧게 기록합니다.

### Pending

- frontend framework
- content format
- schema validator
- deployment target
- test runner
- analytics policy
