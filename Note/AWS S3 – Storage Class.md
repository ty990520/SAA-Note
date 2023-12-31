## AWS S3 및 Glacier의 주요 스토리지 클래스

[참고자료: [Re2021] Amazon S3의 신규 스토리지 클래스(Glacier Instant Retrieval)가 출시되었습니다](https://www.wisen.co.kr/pages/blog/blog-detail.html?idx=12080)

![storage_class](https://dev.wisen.co.kr/_core/_files/naverEditor/13-011.png)

1. **S3 Intelligent-Tiering**:
   - 자동 비용 절감을 위한 데이터의 자동 계층 분류.
   - 접근 패턴이 예측 불가능한 데이터에 적합.
   - 자동으로 데이터를 접근 빈도에 따라 다른 액세스 계층(빈번, 드문)으로 이동.
     
2. **STANDARD**: 
   - 일반적인 사용 사례를 위한 기본 스토리지 클래스.
   - 자주 접근되는 데이터에 적합합니다.

3. **S3 Standard-Infrequent Access (S3 Standard-IA)**:
   - 덜 자주 접근되지만, 빠른 액세스가 필요할 때 사용.
   - 월별로 접근되는 데이터에 대한 저렴한 저장 공간.
   - 보관 기간이 길고 접근 빈도가 낮은 데이터에 적합.

4. **S3 Glacier Instant Retrieval**:
   - 장기 보관을 위한 저렴한 스토리지.
   - 데이터 검색은 밀리초 단위로 가능합니다.

5. **S3 Glacier Flexible Retrieval**:
   - 백업 및 아카이브 데이터를 위한 장기, 저비용 스토리지.
   - 데이터 검색 옵션이 몇 분에서 몇 시간까지 다양합니다.
   - 데이터 복구에 몇 시간 걸림.

6. **S3 Glacier Deep Archive**:
   - 장기간 접근되지 않는 아카이브 데이터를 위한 최저비용 클라우드 저장 공간.
   - 데이터 검색은 몇 시간이 걸립니다.
   - 매우 오랜 기간 동안 접근할 필요가 없는 데이터에 적합.
   - 가장 저렴한 스토리지 클래스.
   - 데이터 복구에 12시간 이상 걸림.

7. **S3 One Zone-Infrequent Access (S3 One Zone-IA)**:
   - 한 가용 영역(AZ)에만 저장되는 자주 접근되지 않는 데이터.
   - 비용 절감을 위해 사용됩니다.
   - 장기 보관을 위한 데이터이지만, 빠른 접근이 필요할 때 사용.
   - 모든 데이터가 하나의 가용 영역(AZ)에만 저장됨.
   - STANDARD_IA보다 저렴하지만, AZ 장애 시 데이터 손실 위험 존재.

8. **S3 on Outposts**:
   - AWS Outposts 환경의 on-premises 데이터에 대한 객체 저장.
   - 로컬 데이터 처리 및 데이터 보관 요구 사항을 충족하기 위해 설계되었습니다.

---

## Infrequent Access 클래스(S3 Standard-IA, One Zone-IA)의 30일 제약 - 

S3 Standard-IA나 One Zone-IA와 같은 `덜 자주 액세스되는` 스토리지 클래스로 데이터를 너무 빨리 옮기면, 데이터의 액세스 패턴과 실제 스토리지 클래스의 목적이 일치하지 않을 수 있습니다. 이로 인해 예상보다 높은 비용이 발생할 수 있습니다. 

예를 들어, 다음과 같은 상황을 생각해보겠습니다:

1. **데이터가 자주 액세스되는 경우**: 만약 S3 Standard에서 S3 Standard-IA로 데이터를 너무 빨리 옮기게 되면, 그 데이터에 자주 액세스하게 될 수 있습니다. S3 Standard-IA는 저장 비용은 낮지만 데이터를 액세스할 때마다 추가 비용이 발생합니다. 따라서 예상보다 더 자주 액세스하게 되면, 그 추가 비용이 누적되어 전체 비용이 더 높아질 수 있습니다.

2. **데이터 전환 비용**: 데이터를 한 스토리지 클래스에서 다른 클래스로 전환할 때도 비용이 발생합니다. 따라서 데이터를 너무 자주 이동시키게 되면, 이러한 전환 비용도 누적될 수 있습니다.

이러한 이유로 AWS는 사용자가 무분별하게 데이터를 'Infrequent Access' 클래스로 옮기는 것을 방지하려고 30일 제약을 둡니다. 이 제약은 데이터의 액세스 패턴과 스토리지 클래스의 비용 특징이 잘 맞도록 돕기 위한 것입니다.
