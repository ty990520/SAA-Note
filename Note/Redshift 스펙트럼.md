## Amazon Redshift 스펙트럼

![image](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2017/07/18/redshift_spectrum-1.gif)

1. **별도의 서비스**: Redshift 스펙트럼은 Amazon Redshift와는 별도로 동작하는 서비스입니다.

2. **S3 데이터 직접 쿼리**: Redshift 스펙트럼을 사용하면, Amazon S3에 저장된 데이터를 직접 쿼리할 수 있습니다. 따라서 Amazon Redshift의 테이블로 데이터를 별도로 로드하거나 이동할 필요가 없습니다.

3. **연산 집약적 작업 효율 처리**: Redshift 스펙트럼은 연산 집약적인 작업 (예: 조건 필터링, 집계)을 스펙트럼 레이어에서 처리하여 클러스터의 부하를 줄입니다. 결과적으로 Redshift 클러스터의 처리 능력을 훨씬 덜 사용하게 됩니다.

4. **구조화 및 반구조화 데이터 처리**: Redshift 스펙트럼을 통해 Amazon S3에 저장된 구조화된 데이터 (예: CSV, Parquet) 및 반구조화된 데이터 (예: JSON)를 효율적으로 쿼리하고 검색할 수 있습니다.

5. **자원 효율성**: Redshift 스펙트럼은 전용 레이어에서 동작하므로, 사용자의 기존 Redshift 클러스터 리소스에 부담을 주지 않으면서 대규모 데이터 처리가 가능합니다.
    - 전용 레이어 : 이는 Redshift 스펙트럼이 기존의 Amazon Redshift 클러스터와 독립적인 자체 컴퓨팅 리소스를 가지고 동작한다는 것을 의미(다른 서버에서 처리해서 결과만 우리에게 반환)

---

## Redshift 클러스터 테이블

Redshift Spectrum을 사용하면 Amazon S3에 저장된 데이터에 대한 `가상의` 테이블을 Redshift에서 정의할 수 있습니다. 이 가상의 테이블은 실제 Redshift 클러스터 내에 데이터를 저장하고 있는 것이 아니라, S3에 있는 데이터를 참조하게 됩니다.

Amazon Redshift Spectrum에서 정의하는 `테이블`은 실제 데이터를 포함하고 있지 않습니다. 대신 Amazon S3에 저장된 데이터에 대한 `참조`나 `인덱스`와 같은 역할을 합니다. 이러한 테이블을 사용하면, 실제 데이터는 Amazon S3에 그대로 남아 있으면서, Redshift에서 마치 그 데이터가 클러스터 내에 있는 것처럼 쿼리를 수행할 수 있습니다.
