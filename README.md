# AWS 서비스 및 기능

## 분석
- Amazon Athena
  - S3버킷에 저장된 데이터를 분석하는 서버리스 쿼리 서비스
  - 서버리스 SQL엔진을 사용한 S3 데이터 분석 시 사용
- AWS Data Exchange
- AWS Data Pipeline
- Amazon EMR
  - 빅 데이터 워크로드를 위한 클러스터 기반 서비스
  - Apache Hadoop 및 Apache Spark와 같은 분산 데이터 처리 프레임워크를 실행
- AWS Glue
    -   ETL 작업을 위한 서비스 (Extract, Transform, Load)
    -   데이터 웨어하우징 및 데이터 통합에서 널리 사용
    -   다양한 데이터 소스에서 데이터를 추출, 변환, 로드하는 작업을 자동화하고 관리
    -   주로 배치 작업에 사용되기 때문에 실시간 처리보다는 약간의 지연이 발생
    -   작업 북마크 : 이미 처리된 데이터를 다시 처리하지 않도록 함
- Amazon Kinesis
  - 수 천 개의 edge 장치로부터 경고 수집 및 저장
- AWS Lake Formation
- Amazon Managed Streaming for Apache Kafka(Amazon MSK)
- Amazon OpenSearch Service(Amazon Elasticsearch Service)
- Amazon QuickSight
  - 데이터 시각화 서비스
  - PostgreSQL용 S3 및 RDS를 비롯한 다양한 데이터소스에서 대화형 대시보드 및 보고서 생성 가능
  - 적절한 사용자 및 그룹과 대시보드를 공유 가능
  - IAM 역할 및 권한을 사용하여 액세스 수준 제어 가능
- Amazon Redshift

## 애플리케이션 통합
- Amazon AppFlow
  - SaaS 애플리케이션과 S3 및 RedShift와 같은 AWS서비스 간에 데이터를 안전하게 전송
  - Salesforce, SAP, Zendesk, Slack, ServiceNow 등
  - 완전 관리형
- AWS AppSync
- Amazon EventBridge(Amazon CloudWatch Events)
  - 서버리스 이벤트 브로커 
- Amazon MQ
  - Apache ActiveMQ 및 RabbitMQ용 관리형 메시지 브로커 서비스
- Amazon Simple Notification Service(Amazon SNS)
  - pub/sub 모델 기반 푸시 알림 서비스
  - 완전관리형 메시징 서비스
- Amazon Simple Queue Service(Amazon SQS)
  - 마이크로서비스, 분산 시스템 및 서버리스 애플리케이션을 분리하고 확장할 수 있는 완전관리형 메시지 대기열 서비스
  - 가시성 시간 제한 : 다른 소비자가 메시지를 처리할 수 없도록 차단하는 시간
- AWS Step Functions

## AWS 비용 관리
- AWS Budgets
- AWS Cost and Usage Report
- AWS Cost Explorer
  - 비용과 사용량을 보고서를 사용하여 분석할 수 있는 도구
  - 세분화된 필터링 기능을 사용하여 리소스 비용에 대한 심층 분석 가능
- Savings Plans

## 컴퓨팅
- AWS Batch
- Amazon EC2
  - 예약 인스턴스 : 미리 해당 서버를 구입하여 사용 -> 비용 절감
  - 온디맨드 인스턴스 : 사용한 만큼 비용을 나중에 지불 
    - 온디맨드 용량 예약 : 용량 보장
  - 스팟 인스턴스 : AWS내에서 남아있는 서버 공간을 빌려서 사용하는 방식 -> 도중에 중지될 가능성이 높음
    - 스팟 블록 : 기간이 정해져있는 스팟 인스턴스 
- Amazon EC2 Auto Scaling
- AWS Elastic Beanstalk
- AWS Outposts
- AWS Serverless Application Repository
- VMware Cloud on AWS
- AWS Wavelength

## 컨테이너
- Amazon Elastic Container Registry(Amazon ECR)
- Amazon Elastic Container Service(Amazon ECS)
- Amazon ECS Anywhere
- Amazon Elastic Kubernetes Service(Amazon EKS)
- Amazon EKS Anywhere
- Amazon EKS Distro

## 데이터베이스
- Amazon Aurora
  - Aurora 복제본 : 읽기작업 확장
- Amazon Aurora Serverless
- Amazon DocumentDB (with MongoDB compatibility)
- Amazon DynamoDB
  - 용량에 맞게 테이블을 자동 조정하므로 별도의 관리 필요 없이 성능 유지 가능 (RDS와의 차이점)
  - 확장성이 뛰어나고 밀리초 단위의 액세스를 지원
  - 주문형 백업 : 전체 백업을 즉시 생성
  - 전역 테이블 : 데이터를 여러 AWS 리전에 자동으로 복제
  - 글로벌 보조 인덱스 : 특정 속성에 대한 추가적인 인덱스를 생성하여 다양한 방법으로 빠르게 쿼리 가능
  - 지정 시간 복구(Point-In-Time Recovery, PITR) : 최근 35일 동안의 데이터를 복구 (지속적인 백업x)
- Amazon ElastiCache
- Amazon Keyspaces (for Apache Cassandra)
- Amazon Neptune
- Amazon Quantum Ledger Database(Amazon QLDB)
- Amazon RDS
  - Auto Scaling을 지원 x
  - Amazon RDS Custom : 기존 OS 및 DB 환경 유지가 필요한 경우 사용(레거시, 사용자 지정, 패키지 어플리케이션)
- Amazon Redshift
- Amazon Timestream

## 개발자 도구
- AWS X-Ray

## 프런트 엔드 웹 및 모바일
- AWS Amplify
- Amazon API Gateway
- AWS Device Farm
- Amazon Pinpoint

## 기계 학습
- Amazon Comprehend
  - 자연어 처리
  - 텍스트에서 유용한 인사이트를 도출
  - Amazon Comprehend Medical
    - 의료 데이터 추출 
- Amazon Forecast
- Amazon Fraud Detector
- Amazon Kendra
- Amazon Lex
- Amazon Polly
- Amazon Rekognition
  - 이미지 인식 및 비디오 분석을 자동화
  - 부적절하거나 불쾌감을 주는 콘텐츠를 감지
  - 얼굴 및 텍스트 탐지
- Amazon SageMaker
  - 사용자가 기계 학습 모델을 쉽게 구축, 학습, 배포할 수 있도록 지원하는 플랫폼 
- Amazon Textract
  - 텍스트 추출 
- Amazon Transcribe
- Amazon Translate

## 관리 및 거버넌스
- AWS Auto Scaling
- AWS CloudFormation
- AWS CloudTrail
  - 리소스 내역 기록 (로깅 서비스)
  - AWS 인프라 전체에서 계정의 활동을 로그하고, 지속적으로 모니터링하여 스토리지, 분석 및 해결 작업을 제어할 수 있음 
- Amazon CloudWatch (모니터링 서비스)
  - 외부사용자와 대시보드를 공유하려는 경우, 간단하게 계정을 등록해서 url로 대시보드 공유 가능 
  -  CloudWatch Logs
      -   주로 로그 모니터링 및 알람 설정에 사용
      -   로그에 대한 복잡한 SQL 쿼리를 실행하는 데에는 적합하지 않음
- AWS Command Line Interface(AWS CLI)
- AWS Compute Optimizer
- AWS Config
  - AWS 리소스의 구성을 추적하고, 원하는 설정과 리소스의 현재 구성이 일치하는지 확인 
  - AWS 리소스 구성을 측정,감사,평가할 수 있는 서비스
  - AWS 리소스 구성을 지속적으로 모니터링 및 기록하고, 원하는 구성을 기준으로 기록된 구성을 자동으로 평가해줌 
- AWS Control Tower
- AWS License Manager
- Amazon Managed Grafana
- Amazon Managed Service for Prometheus
- AWS Management Console
  - 웹 기반 인터페이스 (흔히 말하는 웹 콘솔) 
- AWS Organizations
- AWS Personal Health Dashboard
- AWS Proton
- AWS Service Catalog
- AWS Systems Manager
  -  
- AWS Trusted Advisor
  -  현재 구성에서 비용 절감, 성능 향상, 보안 강화에 도움되는 권장 사항을 제시
- AWS Well-Architected Tool

## 미디어 서비스
- Amazon Elastic Transcoder
- Amazon Kinesis Video Streams

## 마이그레이션 및 전송
- AWS Application Discovery Service
- AWS Application Migration Service(CloudEndure Migration)
- AWS Database Migration Service(AWS DMS)
  - 데이터베이스 마이그레이션
  - 지속적인 복제 : 온라인 상태를 유지하고 마이그레이션 중에 액세스 가능
- AWS DataSync
  - 파일(스토리지) 기반 데이터 전송
  - 온프레미스 스토리지에서 Amazon S3, EFS, FSx로의 데이터 전송
  - 데이터 백업, 데이터 복제 및 데이터 복원
  - 빠른 데이터 전송 속도, 대량의 데이터 전송에 최적화
- AWS Migration Hub
- AWS Server Migration Service(AWS SMS)
- AWS Snow Family
  - AWS Snowcone : 작은 양의 데이터(8TB)를 이동할 때 사용
  - AWS Snowball : 더 큰 데이터를 이동할 때 사용
    - Snowball Standard : 50TB 또는 80TB의 용량
    - Snowball Edge : 100TB 이상의 용량
  - AWS Snowmobile : 매우 큰 양의 데이터(수PB)를 전송하는 데 사용
- AWS Transfer Family
  - SFTP, FTPS, FTP 프로토콜을 지원하여 실시간 파일 전송을 제공
  - 다른 사용자와의 파일 공유나 업로드 및 다운로드 지원 

## 네트워킹 및 콘텐츠 전송
- Amazon CloudFront
  - 전 세계에 분산된 엣지 로케이션에서 사용자에게 콘텐츠를 더 빠르게 제공 가능 (CDN)
  - DDoS 대처 가능, 가용성 보호
- AWS Direct Connect
  - 온프레미스 환경과 AWS 간의 전용 네트워크 연결 (전용선)
  - 인터넷 대역폭을 사용하지 않고 AWS와 직접 연결을 통해 데이터를 전송
  - 일관된 짧은 지연 시간과 고성능의 연결 
- Elastic Load Balancing(ELB)
- AWS Global Accelerator
  - 네트워크 가속 서비스 (TCP/UDP 4계층에서 동작)
  - 글로벌 IP 주소를 제공하여 사용자가 가장 가까운 엔드포인트로 트래픽을 라우팅할 수 있도록 지원
- AWS PrivateLink
  - 데이터를 인터넷에 노출하지 않고 VPC와 AWS 서비스 간에 연결을 설정
  - VPC와 VPC를 연결하는 경우 VPC 내부에 있는 서비스에 모두 접근할 우려가 있으므로 VPC가 아니라 서비스를 대상으로 연결함 
- Amazon Route 53
  - 사용자의 도메인에 대한 DNS 레코드를 관리
  - 다양한 라우팅 정책(예: 지연 시간 기반, 지역 기반, 가중치 기반 라우팅 등)을 제공하여, 글로벌 트래픽을 지능적으로 라우팅 가능
- AWS Transit Gateway
- Amazon VPC
- AWS VPN
  - Direct Connect 연결이 실패한 경우에 백업으로 작동 가능 (느린 트래픽을 허용하는 경우)

## 보안, 아이덴티티 및 규정 준수
- AWS Artifact
- AWS Audit Manager
- AWS Certificate Manager(ACM)
  - CloudFront 사용 시 us-east-1(버지니아 북부)에서만 ACM 사용 가능 (그 외에는 상관없음)
- AWS CloudHSM
- Amazon Cognito
- Amazon Detective
- AWS Directory Service
  -  사용자 정보를 관리하고 조직의 컴퓨터와 기타 리소스를 연결해주는 서비스
  -  사용자의 인증 및 권한 부여, 디렉터리 기반의 ID 관리 서비스
- AWS Firewall Manager
  - 중앙에서 방화벽 규칙을 관리하는 서비스
  - 조직의 여러 계정 및 리소스에 대한 WAF 규칙, Shield Advanced 보호, VPC 보안그룹 및 Network Firewall 및 Route53 Resolver DNS Firewall 규칙을 중앙에서 구성할 수 있음
- Amazon GuardDuty
  - 계정 보호 서비스
  - AWS 계정 및 환경에서 악의적 활동을 모니터링하고 상세한 보안 결과를 제공하여 가시성 및 해결을 촉진하는 위협 탐지 서비스
- AWS Identity and Access Management(IAM)
- Amazon Inspector
  - 보안취약점 자동 스캔 -> 권장사항 알림 (자동 조치 X)
  - AWS 환경에서의 애플리케이션 보안 상태를 주기적으로 검사하고, 발견된 취약점이나 문제점에 대한 권장 사항을 제공
  - 호스트 수준의 취약성 평가 o, 콘텐츠 자체를 스캔하지는 않음 (Macie와의 차이점)
- AWS Key Management Service(AWS KMS)
- Amazon Macie
  - 개인 식별 정보(PII)와 같은 민감한 데이터를 자동으로 검색, 분류, 보호하는 관리형 서비스
  - S3에서 Macie를 활성화하면 업로드된 객체에서 PII를 자동으로 검색
- AWS Network Firewall
  - VPC로 들어오고 나가는 네트워크 트래픽을 필터링할 수 있음
  - 트래픽 흐름 검사 및 트래픽 필터링 기능 제공
- AWS Resource Access Manager(AWS RAM)
- AWS Secrets Manager
  - RDS 또는 Aurora의 자격증명을 여러 리전에서 교체하기 위한 솔루션
  - 자동으로 데이터베이스 비밀번호 교체 지원
  - 애플리케이션에 자격증명 하드코딩 제거 가능
- AWS Security Hub
- AWS Shield
  - DDoS 방어 서비스
  - 두 가지 버전 존재
    - AWS Shield Standard : 소규모 공격에 적합
    - AWS Shield Advanced : 대규모 공격에 적합   
- AWS Single Sign-On
  - 한 번 로그인하면 연관된 서비스들을 추가 로그인 없이 사용할 수 있게 함 
- AWS WAF

## 서버리스
- AWS AppSync
- AWS Fargate
  - EC2인스턴스의 서버나 클러스터를 관리할 필요 없이 컨테이너를 실행하기 위해 ECS에 사용할 수 있는 기술 
- AWS Lambda

## 스토리지
- AWS Backup
- Amazon Elastic Block Store(Amazon EBS)
  - 하나의 EC2 인스턴스와 연결됨
  - 프로비저닝된 IOPS : 고성능이 필요한 애플리케이션에서 일관된 성능 제공
- Amazon Elastic File System(Amazon EFS)
  - 표준 파일 시스템
  - 자동 확장되며 가용성이 높음
  - 여러 EC2 인스턴스에서 동시 접속 가능 
- Amazon FSx(모든 유형)
  - 완전관리형 파일 스토리지
  - NetApp ONTAP, OpenZFS, Windows File Server, Lustre의 4가지 파일시스템을 지원
- Amazon S3
  - 일반적인 객체 저장 및 빠른 액세스에 적합
  - 거의 즉시 액세스 가능
- Amazon S3 Glacier
  - 장기적인 아카이빙 및 백업에 특화
  - 접근 빈도가 낮은 데이터를 매우 저렴한 비용으로 저장 가능
  - 검색 느림
- AWS Storage Gateway
