## Redshift에 데이터를 로드하는 방법

1. **Amazon Kinesis Data Firehose**
    - Kinesis Firehose가 다양한 소스로부터 데이터를 받아서 Redshift로 전달
    - S3에 데이터를 추가하면 Firehose가 자동으로 COPY 명령어를 사용해서 Redshift에 복사
2. **S3 using COPY command**
    - Amazon S3에 저장된 데이터를 Redshift로 로드하는데 가장 일반적으로 사용
    - 사용자는 먼저 데이터를 Amazon S3 버킷에 업로드하고, 그런 다음 Redshift의 COPY 명령을 사용하여 S3에서 Redshift로 데이터를 병렬로 빠르게 로드
3. **EC2 instance JDBC driver**
    - 애플리케이션 코드에서 JDBC를 통해 직접 Redshift로 데이터 전송
    - INSERT 문을 사용하여 레코드를 하나씩 추가 or 배치 삽입을 사용하여 여러 레코드를 동시에 추가(이게 더 효율적)
