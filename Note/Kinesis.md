## Amazon Kinesis
실시간 빅 데이터 스트리밍을 가능하게 하는 AWS의 플랫폼

Kinesis Data Streams와 Kinesis Data Firehose 두 서비스로 분류됨

<br>

### Kinesis Data Streams (KDS)

1. **Custom Consumer**: KDS는 사용자가 자신의 데이터 소비자(예: EC2 인스턴스에서 실행 중인 애플리케이션)를 작성하고 관리해야 합니다. 이는 훨씬 더 유연한 환경을 제공하지만, 관리 부담도 증가합니다.

2. **Real-time Processing**: KDS는 실시간 데이터 처리에 초점을 맞춰, 데이터를 스트림에서 거의 실시간으로 소비할 수 있도록 합니다.

3. **Manual Scaling**: KDS의 샤드(shard)라고 하는 스트림 용량 단위를 수동으로 스케일링해야 합니다.

4. **Retention Period**: KDS는 기본적으로 24시간 동안 데이터를 유지하며, 최대 7일까지 확장할 수 있습니다.

<br>

### Kinesis Data Firehose (KDF)

1. **Fully Managed Service**: KDF는 완전 관리형 서비스로서, 데이터를 로드하고, 변환하고, 전달하는 과정을 사용자 대신 관리합니다.

2. **Near Real-time**: KDF는 거의 실시간(수 초의 지연 시간을 가짐)으로 데이터를 로드합니다.

3. **Automatic Scaling**: KDF는 자동으로 스케일링을 처리하므로, 사용자는 이에 대해 걱정할 필요가 없습니다.

4. **No Data Storage**: KDF는 데이터를 자체적으로 저장하지 않고, 다른 AWS 서비스(예: S3, Redshift, Elasticsearch 등)로 전달합니다.

5. **Transformations**: KDF는 데이터를 다른 AWS 서비스로 전송하기 전에 AWS Lambda를 통한 데이터 변환 기능을 제공합니다.

<br>

### 요약

- **Kinesis Data Streams**: 높은 유연성을 제공하지만, 사용자가 더 많은 관리 작업을 수행해야 합니다.
  
- **Kinesis Data Firehose**: 사용자 친화적이고 완전 관리형 서비스로서, 다양한 AWS 목적지로 데이터를 손쉽게 전달할 수 있습니다.

