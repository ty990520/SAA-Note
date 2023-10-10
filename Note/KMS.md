## KMS

- 시험 tip : '암호화'라는 단어가 나오면 대부분 KMS 암호화를 말함
- KMS 서비스가 사용자를 대신해서 암호화 키를 관리한다는 개념
- 리전 단위
- **강점**
    - `CloudTrail`을 통해 KMS 키를 사용한 모든 API 호출을 감사(Audit)할 수 있음
    - EBS, S3, RDS, SSM, ... 등 암호화를 원하는 경우 KMS를 활성화하면 됨 (편리!)
    - 애플리케이션 코드에 직접 비밀 데이터를 하드코딩하지 말고 KMS API Call을 사용 (변수로 처리해버리면 됨)

<br>

### KMS 키 종류 2가지
  -  대칭키 : 데이터 암복호화에 하나의 키만 필요
      -  KMS가 통합된 모든 AWS 서비스는 대칭키를 사용
      -  사용자는 절대 키에 직접적으로 접근할 수 없으며 오로지 API 콜을 통해 사용할 수 있음
  -  비대칭키 : 데이터 암호화(퍼블릭키)와 복호화(프라이빗키)에 각각 키가 필요, 총 2개의 키가 있음
      -  사용자는 KMS에서 퍼블릭키만 다운로드 가능 (프라이빗키에는 API 콜만 가능)

<br>

### KMS 서비스 타입
  -  AWS Owned Keys
      -  무료
      -  SSE-S3 타입의 암호화를 사용하거나 SSE DynamoDB를 사용할 때 default 키
  -  AWS Managed Key
      -  무료
      -  `aws/서비스이름` (ex. aws/rds, aws/ebs...)
  - Customer managed key
      - Customer managed keys created in KMS: 
          - AWS KMS에서 직접 생성된 키
          - $1 / month
          - 사용자는 AWS KMS 콘솔, CLI 또는 SDK를 사용하여 키를 생성하며, 이 키는 AWS KMS 내에서 관리됨
      - Customer managed keys imported (must be symmetric key): 
          - 사용자가 외부에서 생성한 키(예: 자체 하드웨어 보안 모듈(HSM) 또는 다른 키 관리 시스템에서)를 AWS KMS에 가져온 경우
          - $1 / month
          - KMS로 가져오려는 키가 대칭 키여야 함 
      -  pay for API call to KMS ($0.03 / 10000 calls)
   
<br>

### KMS Key Policies
  -  기본 키 정책
      - 사용자가 특정한 커스텀 KMS 키 정책을 제공하지 않았을 때 생성 (기본값)
      - 계정에 있는 모든 유저가 이 키에 액세스할 수 할 수 있음
  -  커스텀 키 정책
      - 키에 액세스할 수 있는 user와 role을 정의
      - 키를 누가 관리할지 정의
      - 다른 계정에서 우리 계정의 KMS 키를 사용하도록 승인 가능
