## Athena
-   S3버킷에 저장된 데이터를 분석하는 서버리스 쿼리 서비스 (federated query 기능을 사용하면 RDS,Redshift,Glue Data Catalog,Apache HBase 등의 다양한 데이터 소스 사용 가능)
-   표준 SQL을 사용해야함
-   S3에 저장된 데이터에 대해 SQL 쿼리를 바로 실행할 수 있음 (별도의 인프라스트럭처를 설정하거나 관리할 필요X)
-   특히 JSON 형식과 같은 반정형 데이터에 대한 쿼리에 적합 (CSV, ORC, Avro, Parquet 등의 형식 지원)
-   스캔된 데이터의 TB당 고정 가격 지불(파일당 크기를 크게 만드는 것이 오히려 더 효율적->압축 권장, 데이터셋 파티셔닝, AWS Glue를 사용해서 ORC, Parquet 형식으로 만들어서 사용)
-   Amazon QuickSight와 함께 사용하는 경우가 많음 -> 보고서와 대시보드 생성
-   사용사례 : 임시 쿼리 수행, 비즈니스 인텔리전스 분석 및 보고, AWS 서비스에서 발생하는 모든 로그를 쿼리 분석
-   시험 tip : __서버리스 SQL엔진을 사용한 S3 데이터 분석__ 
