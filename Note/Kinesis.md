## Amazon Kinesis
실시간 빅 데이터 스트리밍을 가능하게 하는 AWS의 플랫폼

Kinesis Data Streams와 Kinesis Data Firehose 두 서비스로 분류됨

[참고 블로그](https://jaeyeong951.medium.com/aws-kinesis-data-stream-vs-data-firehose-10102d949741)


<br>

### 1. Kinesis Data Streams (KDS) - low latency streaming service
**Kinesis Data Streams**는 실시간 데이터 스트림을 제공하는 서비스입니다. 이 서비스는 대량의 실시간 데이터를 연속적으로 수집하고, 처리하여 다양한 대상으로 전송하는 데 사용됩니다.
- Kinesis Data Stream 은 실시간으로 data 들을 받아들일 수 있는 입구이자 저장소로서의 역할
- 한 시스템이 실시간으로 Data Stream 에 데이터를 전송하면 해당 Data Stream 을 listening 하고있던 다른 한 시스템이 해당 데이터를 받아 처리
- pipeline 이자 메시지 큐와 비슷한 역할


**특징 및 사용 케이스**:
- **실시간 데이터 수집**: 웹 사이트 클릭 스트림, 로그, 소셜 미디어, 그리고 다른 실시간 소스에서 발생하는 데이터를 연속적으로 수집할 수 있습니다.
- **커스텀 처리**: KDS는 AWS Lambda, Amazon EC2, Kinesis Data Analytics와 같은 다양한 소비자로 데이터를 전송하여 실시간 분석 및 다른 처리 작업을 할 수 있게 합니다.
- **장기 보존**: KDS는 최대 7일 동안 데이터를 보존할 수 있습니다.

<br>

### 2. Kinesis Data Firehose (KDF) - data transfer service
**Kinesis Data Firehose**는 실시간 데이터를 쉽게 로드하고 분석하기 위해 자동으로 다양한 AWS 서비스로 스트리밍할 수 있도록 설계된 완전 관리형 서비스입니다.
- Kinesis Data Firehose 의 주목적은 미리 정의된 목적지(Destination)에 데이터를 안전하게 전달(Deliver)하는 것
  - 여기서 목적지라 함은 S3 bucket, ElasticSearch, Amazon Redshift 등 -> data lake의 역할


**특징 및 사용 케이스**:
- **완전 관리형 서비스**: KDF는 데이터를 자동으로 수집, 변환 및 전송하는 관리형 서비스입니다.
- **데이터 변환**: AWS Lambda를 사용하여 데이터를 처리하고 변환할 수 있습니다.
- **다양한 대상 지원**: Amazon S3, Amazon Redshift, Amazon Elasticsearch Service, Splunk 등 다양한 대상에 데이터를 전송할 수 있습니다.


<br>

**요약**
- KDS (Kinesis Data Streams)는 `실시간 데이터 수집`에 중점
- KDF (Kinesis Data Firehose)는 `자동화된 데이터 전송과 변환`에 중점
- Data Stream 은 길게는 일주일 까지 데이터를 잠시 저장할 수 있지만 (Stream 의 역할을 하기 때문에), Firehose 는 데이터를 잠시라도 들고있을 수 없음 (말그대로 Transfer 의 역할만 수행)

