## AWS Organizations 와 AWS Control Tower
모두 AWS 계정과 조직의 리소스를 관리하고 거버넌스를 적용하는 서비스

1. **AWS Organizations**:
    - AWS 계정의 중앙집중적인 관리를 가능하게 합니다.
    - 계정을 생성하고, 계정 간에 리소스를 공유하며, 계정을 조직 구조에 맞게 그룹화할 수 있습니다.
    - `서비스 제어 정책 (Service Control Policies, SCPs)`을 사용하여 조직 전체 또는 특정 계정에 대한 AWS 서비스의 사용을 제한할 수 있습니다.


2. **AWS Control Tower**:
    - AWS Control Tower는 AWS Organizations를 기반으로 작동합니다.
    - AWS 환경의 자동 설정 및 구성 관리를 지원합니다.
    - 블루프린트를 사용하여 조직의 모든 AWS 계정에 거버넌스 및 베스트 프랙티스를 적용합니다.
    - `데이터 상주 가드레일`과 같은 고급 기능을 제공하여 데이터가 올바른 지역에 저장되도록 강제합니다.


> AWS Organizations : 조직의 AWS 계정을 중앙에서 관리할 수 있는 `기본적인 틀`을 제공

> AWS Control Tower : `AWS Organizations의 기능을 확장`하고, 추가적인 자동화 및 거버넌스 기능을 제공

> AWS Control Tower를 사용하려면 AWS Organizations도 활성화되어 있어야 함

