# AWS 서비스 및 기능

## 분석
- Amazon Athena
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
- Amazon CloudWatch
  -  CloudWatch Logs
      -   주로 로그 모니터링 및 알람 설정에 사용
      -   로그에 대한 복잡한 SQL 쿼리를 실행하는 데에는 적합하지 않음
- AWS Command Line Interface(AWS CLI)
- AWS Compute Optimizer
- AWS Config
  - AWS 리소스 구성을 측정,감사,평가할 수 있는 서비스
  - AWS 리소스 구성을 지속적으로 모니터링 및 기록하고, 원하는 구성을 기준으로 기록된 구성을 자동으로 평가해줌 
- AWS Control Tower
- AWS License Manager
- Amazon Managed Grafana
- Amazon Managed Service for Prometheus
- AWS Management Console
- AWS Organizations
- AWS Personal Health Dashboard
- AWS Proton
- AWS Service Catalog
- AWS Systems Manager
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
- AWS Direct Connect
- Elastic Load Balancing(ELB)
- AWS Global Accelerator
- AWS PrivateLink
- Amazon Route 53
- AWS Transit Gateway
- Amazon VPC
- AWS VPN

## 보안, 아이덴티티 및 규정 준수
- AWS Artifact
- AWS Audit Manager
- AWS Certificate Manager(ACM)
- AWS CloudHSM
- Amazon Cognito
- Amazon Detective
- AWS Directory Service
- AWS Firewall Manager
  - 중앙에서 방화벽 규칙을 관리하는 서비스
  - 조직의 여러 계정 및 리소스에 대한 WAF 규칙, Shield Advanced 보호, VPC 보안그룹 및 Network Firewall 및 Route53 Resolver DNS Firewall 규칙을 중앙에서 구성할 수 있음
- Amazon GuardDuty
  - 계정 보호 서비스
  - AWS 계정 및 환경에서 악의적 활동을 모니터링하고 상세한 보안 결과를 제공하여 가시성 및 해결을 촉진하는 위협 탐지 서비스
- AWS Identity and Access Management(IAM)
- Amazon Inspector
- AWS Key Management Service(AWS KMS)
- Amazon Macie
- AWS Network Firewall
  - VPC로 들어오고 나가는 네트워크 트래픽을 필터링할 수 있음
  - 트래픽 흐름 검사 및 트래픽 필터링 기능 제공
- AWS Resource Access Manager(AWS RAM)
- AWS Secrets Manager
  - RDS 또는 Aurora의 자격증명을 여러 리전에서 교체하기 위한 솔루션
  - 자동으로 데이터베이스 비밀번호 교체 지원
- AWS Security Hub
- AWS Shield
- AWS Single Sign-On
- AWS WAF

## 서버리스
- AWS AppSync
- AWS Fargate
- AWS Lambda

## 스토리지
- AWS Backup
- Amazon Elastic Block Store(Amazon EBS)
- Amazon Elastic File System(Amazon EFS)
- Amazon FSx(모든 유형)
- Amazon S3
- Amazon S3 Glacier
- AWS Storage Gateway
