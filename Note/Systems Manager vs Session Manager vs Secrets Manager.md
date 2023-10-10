## Systems Manager vs Session Manager vs Secrets Manager

1. **AWS Systems Manager (SSM)**: 
    - AWS 리소스의 가시성과 운영을 개선하는 도구들의 집합입니다.
    - 여기에는 인스턴스의 설정을 중앙에서 관리하는 **Parameter Store**, 인스턴스의 패치 관리, 자동화 스크립트 실행 등의 다양한 기능이 포함됩니다.

2. **Session Manager**: 
    - AWS Systems Manager의 하위 기능 중 하나입니다.
    - SSH 또는 RDP 없이 EC2 인스턴스나 온-프레미스 인스턴스에 안전하게 접속할 수 있게 해줍니다. 
    - 이를 통해 키나 비밀번호 관리 없이 인스턴스에 접근이 가능합니다.

3. **AWS Secrets Manager**:
    - 민감한 정보, 예를 들면 데이터베이스 암호나 API 키 같은 것들을 안전하게 저장하고 관리하는 서비스입니다.
    - 주기적인 암호 교체와 같은 기능도 제공하여, 보안 규정 준수를 쉽게 만들어줍니다.

<br>

### `SSM Parameter Store`의 `SecureString` 옵션 vs `AWS Secrets Manager`

- 공통점
    - 둘 다 보안 정보를 안전하게 저장하고 관리하는 데 사용되며, KMS(Key Management Service)를 이용해 해당 정보를 암호화합니다. 
- 차이점
    - **SSM Parameter Store (SecureString)**:
         - 설정 데이터나 비밀 번호, 데이터베이스 연결 문자열과 같은 구성 정보를 중앙에서 저장하고 관리하는 데 유용합니다.
         - 계층 구조를 사용해 파라미터를 구조화하고 IAM으로 권한을 세밀하게 제어할 수 있습니다.
         - 비용: `Parameter Store`의 표준 파라미터는 무료로 제공되며, 고급 파라미터에는 추가 비용이 발생할 수 있습니다.
    - **AWS Secrets Manager**:
         - 주요 목적은 암호, 토큰, API 키와 같은 민감한 정보를 관리하는 것입니다.
         - 자동 암호 회전 기능이 내장되어 있어, 주기적으로 암호를 변경할 수 있습니다. 이는 RDS, Redshift, DocumentDB와 같은 AWS 데이터베이스 서비스와 통합되어 쉽게 암호 변경 작업을 자동화할 수 있습니다.
         - 비용: 암호 저장 및 암호화 요청에 따른 비용이 있습니다.
- 예를 들어, 주기적인 암호 변경 및 자동화가 필요한 경우 `Secrets Manager`가 더 적합할 수 있습니다. 반면, 단순한 구성 데이터나 계층 구조의 파라미터 저장에는 `Parameter Store`가 더 적합할 수 있습니다.
