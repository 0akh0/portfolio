# 버그 고치는 게임 개발 프로젝트

이 프로젝트는 플레이어가 게임 개발자가 되어 자신이 개발 중인 게임의 버그를 발견하고 수정하는 게임을 개발하는 프로젝트입니다. 본 프로젝트에서 ***저는 게임 기획을 담당하여 게임의 핵심 컨셉, 플레이 방식, 버그 종류 및 해결 메커니즘, 플로우차트 등 게임의 전반적인 시스템을 설계했습니다.*** 또한 엔딩 분기 시스템과 플레이어 진행 경로를 구상하여 게임의 재미 요소를 극대화했습니다.

## 프로젝트 개요

### 회사 소개

4명으로 구성된 소규모 게임 개발 회사로, 각 멤버가 기획, 프로그래밍, 디자인, 레벨 디자인 등 특화된 역할을 담당하고 있습니다.

### 게임 컨셉

플레이어는 게임 개발자로서 출시일이 얼마 남지 않은 자신의 게임을 베타 테스트하며 다양한 버그를 발견하고 수정하는 임무를 맡게 됩니다. 게임 내에서는 모든 레벨의 개발이 완료되어 있고 디버깅만 남은 상태이며, 플레이어는 출시일 전에 모든 버그를 해결해야 합니다.

### 엔딩 시스템

출시일은 총 3번 미룰 수 있으며, 플레이어의 선택과 성과에 따라 다양한 엔딩을 경험할 수 있습니다:

- **퍼펙트 엔딩**: 출시일을 한 번도 미루지 않고 모든 버그 해결 시 게임이 호평을 받음
- **굿 엔딩**: 출시일을 한 번이라도 미뤘지만 모든 버그 해결 시 긍정적인 평가를 받음
- **배드 엔딩**: 출시일을 모두 미루고도 버그를 해결하지 못할 경우 혹평을 받음


## 게임플레이 메커니즘

플레이어는 기본적으로 간단한 게임을 플레이하며 버그를 발견합니다. 주인공의 프로그래밍 실력이 뛰어나지 않기 때문에, 게임 내 가상 인터넷을 통해 해결책을 검색하거나 동료 개발자에게 도움을 요청하여 버그를 수정해나가는 방식으로 진행됩니다.

### 버그 종류 및 해결 방법

#### 1. 미싱 텍스쳐 버그

화면에 텍스쳐가 누락되어 오브젝트 식별이 어렵고 상호작용이 불가능한 상태가 됩니다.

**해결 방법**: 인터넷에서 적절한 이미지를 찾아 적용

미싱 텍스쳐 버그 이미지

![image](https://github.com/user-attachments/assets/cd0c929e-6a50-4d9e-8868-5db52eb31eb9)


#### 2. 텍스트 깨짐 버그

게임 내 텍스트가 깨져서 표시되는 버그입니다.

**해결 방법**: 게임 속 가상 PC에서 해당 텍스트 파일을 찾아 수정

텍스트 깨짐 버그 이미지

![image](https://github.com/user-attachments/assets/86103c59-af6e-45a4-b94d-00e2a41343b4)


#### 3. 성능 관련 버그 (렉)

게임 플레이 중 렉이 발생하는 성능 문제입니다.

**해결 방법**:

- 게임 속 가상 PC의 RAM 할당량 증가
- 불필요한 백그라운드 프로세스 종료
- 게임 품질 설정 조정
- 소스 코드 수정 (근본적 해결책)

성능 버그 이미지

![image](https://github.com/user-attachments/assets/352a4749-2b0e-408a-a325-90b0986181f6)


## 게임 플로우차트

아래 플로우차트는 제가 게임 기획 단계에서 설계한 전체 게임 흐름을 보여줍니다. 메인화면에서 시작하여 다양한 상호작용 경로와 버그 해결 과정을 시각화했습니다.

게임 플로우차트

![image01](https://github.com/user-attachments/assets/87c8c085-8a03-4b25-adc6-db3b7609091f)



## 개발 계획

### 개발 인원

- 기능구현: 2명
- 레벨디자인: 1명
- 그래픽 디자인: 1명
- **게임 기획**: 본인 담당


### 개발 일정

- **콘셉트 및 기획 단계** (2개월): 게임 컨셉 개발, 시스템 설계, 플로우차트 작성
- **그래픽 및 레벨 디자인** (2개월): 캐릭터, 환경, UI 디자인 및 레벨 구조 설계
- **기능 구현** (2개월): 코어 메커니즘 프로그래밍, 버그 시스템 구현
- **베타 테스트** (2개월): 내부 테스팅, 피드백 수집 및 기능 조정
- **오픈 베타** (1개월): 제한된 사용자 대상 공개 테스트
- **정식 출시 및 사후 지원**: 지속적인 업데이트 및 커뮤니티 관리


## 비즈니스 전략

### 투자 계획

- 게임 개발 예산: 약 2억원
- 마케팅 예산: 약 1억원


### 마케팅 전략

- 스팀 플랫폼을 통한 게임 배포
- 베타 버전 무료 제공으로 초기 사용자 확보
- 콘텐츠 크리에이터에게 무료 키 제공하여 홍보 효과 극대화
- 유튜브 및 구글 광고를 통한 타겟 마케팅


## 기대 효과

이 프로젝트는 게임 개발의 실제 과정을 메타적으로 표현하면서도 플레이어에게 재미있는 퍼즐 경험을 제공할 것으로 기대됩니다. 게임 개발자들과 일반 게임 애호가 모두에게 흥미로운 경험을 제공하며, 독특한 컨셉으로 인디 게임 시장에서 차별화된 위치를 확보할 수 있을 것입니다.
