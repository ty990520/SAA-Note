# SAA-Note
AWS Certified Solutions Architect - Associate 정리 노트

- S3 Transfer Acceleration
  -  Amazon S3에 데이터를 빠르게 업로드하거나 다운로드하기 위한 기능
  -  고속 인터넷 연결을 갖춘 사이트에서 글로벌 S3 버킷으로 큰 데이터를 빠르게 업로드할 때 유용
    
-  멀티파트 업로드
    -   큰 객체를 여러 부분으로 분할하고 각 부분을 독립적으로, 동시에 업로드할 수 있도록 함
    -   업로드의 속도와 신뢰성을 향상
    
-  AWS Snowball Edge
    -   대량의 데이터를 AWS로 이동하기 위한 물리적 디바이스
    -   주로 멀티테라바이트(TB)에서 페타바이트(PB) 수준의 데이터 이동을 위한 용도
    -   업로드의 속도와 신뢰성을 향상
 
-  Amazon Athena
    -   서버리스 쿼리 서비스
    -   S3에 저장된 데이터에 대해 SQL 쿼리를 바로 실행할 수 있음 (별도의 인프라스트럭처를 설정하거나 관리할 필요X)
    -   특히 JSON 형식과 같은 반정형 데이터에 대한 쿼리에 적합
 
-  Amazon Redshift
    -   완전 관리형 데이터 웨어하우스 서비스
    -   대규모 데이터 세트를 저장하고 SQL 쿼리를 사용하여 분석하는 데 최적화
    -   빠른 쿼리 성능을 제공하기 위해 열 기반 스토리지 및 병렬 쿼리 실행을 활용

-  Amazon CloudWatch Logs
    -   주로 로그 모니터링 및 알람 설정에 사용
    -   로그에 대한 복잡한 SQL 쿼리를 실행하는 데에는 적합하지 않음
 
-  AWS Glue
    -   ETL 작업을 위한 서비스 (Extract, Transform, Load)
    -   데이터 웨어하우징 및 데이터 통합에서 널리 사용
    -   다양한 데이터 소스에서 데이터를 추출, 변환, 로드하는 작업을 자동화하고 관리
 
-  Amazon EMR
    -   빅 데이터 워크로드를 위한 클러스터 기반 서비스
    -   Apache Hadoop 및 Apache Spark와 같은 분산 데이터 처리 프레임워크를 실행
