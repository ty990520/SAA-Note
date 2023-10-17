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
- Amazon MQ
- Amazon Simple Notification Service(Amazon SNS)
- Amazon Simple Queue Service(Amazon SQS)
  - 마이크로서비스, 분산 시스템 및 서버리스 애플리케이션을 분리하고 확장할 수 있는 완전관리형 메시지 대기열 서비스
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
  - 비용 절감 -> 예약 인스턴스 사용
  - 용량 보장 -> 온디맨드 용량 예약 
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
- Amazon Aurora Serverless
- Amazon DocumentDB (with MongoDB compatibility)
- Amazon DynamoDB
  - 용량에 맞게 테이블을 자동 조정하므로 별도의 관리 필요 없이 성능 유지 가능 (RDS와의 차이점)
  - 확장성이 뛰어나고 밀리초 단위의 액세스를 지원
- Amazon ElastiCache
- Amazon Keyspaces (for Apache Cassandra)
- Amazon Neptune
- Amazon Quantum Ledger Database(Amazon QLDB)
- Amazon RDS
  - Auto Scaling을 지원 x 
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
- Amazon Forecast
- Amazon Fraud Detector
- Amazon Kendra
- Amazon Lex
- Amazon Polly
- Amazon Rekognition
- Amazon SageMaker
- Amazon Textract
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
- AWS Well-Architected Tool

## 미디어 서비스
- Amazon Elastic Transcoder
- Amazon Kinesis Video Streams

## 마이그레이션 및 전송
- AWS Application Discovery Service
- AWS Application Migration Service(CloudEndure Migration)
- AWS Database Migration Service(AWS DMS)
- AWS DataSync
- AWS Migration Hub
- AWS Server Migration Service(AWS SMS)
- AWS Snow Family
- AWS Transfer Family

## 네트워킹 및 콘텐츠 전송
- Amazon CloudFront
  - 전 세계에 분산된 엣지 로케이션에서 사용자에게 콘텐츠를 더 빠르게 제공 가능 (CDN)
- AWS Direct Connect
  - 온프레미스 환경과 AWS 간의 전용 네트워크 연결 (전용선)
  - 인터넷 대역폭을 사용하지 않고 AWS와 직접 연결을 통해 데이터를 전송   
- Elastic Load Balancing(ELB)
- AWS Global Accelerator
  - 네트워크 가속 서비스 (TCP/UDP 4계층에서 동작)
  - 사용자를 가장 낮은 지연 시간으로 AWS 엔드포인트로 라우팅
  - 지역 간 자동 장애 조치를 제공하여 한 지역에서의 실패 시 트래픽을 다른 지역으로 자동으로 리라우팅
- AWS PrivateLink
- Amazon Route 53
  - 사용자의 도메인에 대한 DNS 레코드를 관리
  - 다양한 라우팅 정책(예: 지연 시간 기반, 지역 기반, 가중치 기반 라우팅 등)을 제공하여, 글로벌 트래픽을 지능적으로 라우팅 가능
- AWS Transit Gateway
- Amazon VPC
- AWS VPN

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
- AWS Security Hub
- AWS Shield
  - DDoS 방어 서비스
  - 두 가지 버전 존재
    - AWS Shield Standard : 소규모 공격에 적합
    - AWS Shield Advanced : 대규모 공격에 적합   
- AWS Single Sign-On
- AWS WAF

## 서버리스
- AWS AppSync
- AWS Fargate
- AWS Lambda

## 스토리지
- AWS Backup
- Amazon Elastic Block Store(Amazon EBS)
  - 하나의 EC2 인스턴스와 연결됨
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
