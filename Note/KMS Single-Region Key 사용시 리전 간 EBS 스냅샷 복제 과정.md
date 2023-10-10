## KMS Single-Region Key 사용시 다른 리전으로 EBS 스냅샷을 복제하는 과정

![kms](https://private-user-images.githubusercontent.com/48792230/273949395-25b2fc8e-6b40-406e-8f3c-f362a229213d.jpg?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTEiLCJleHAiOjE2OTY5NDc4NzgsIm5iZiI6MTY5Njk0NzU3OCwicGF0aCI6Ii80ODc5MjIzMC8yNzM5NDkzOTUtMjViMmZjOGUtNmI0MC00MDZlLThmM2MtZjM2MmEyMjkyMTNkLmpwZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFJV05KWUFYNENTVkVINTNBJTJGMjAyMzEwMTAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjMxMDEwVDE0MTkzOFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTg3N2RlYWYwYjYxNTIwZTUxNDNlNGQ3OTM5ZjBlYzI2NTYzYTQ0MjgzMmNjZGU4ZjNjZDczYjQwMjAzZDFiMWImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.9xi9YJRpVveaHDpc1PafVkudZnMDi51wumOJ_GR3Xrw)

1. **원본 리전의 EBS 볼륨**: 이 볼륨은 "A"라는 KMS 키로 암호화되어 있습니다.

2. **스냅샷 생성**: 원본 리전에서 EBS 볼륨의 스냅샷을 생성하면, 이 스냅샷도 "A"라는 KMS 키로 암호화됩니다.

3. **다른 리전으로 스냅샷 복사**: 이 스냅샷을 다른 리전으로 복사하려고 할 때, 목적지 리전의 "B"라는 KMS 키를 지정할 수 있습니다. 이 때의 과정이 중요한데, AWS는 백그라운드에서 다음 작업을 수행합니다:
   - 원본 리전에서 스냅샷 데이터를 "A"라는 KMS 키로 복호화합니다.
   - 이 복호화된 데이터를 목적지 리전으로 전송합니다.
   - 목적지 리전에서 "B"라는 KMS 키로 이 데이터를 다시 암호화합니다.
   
4. **복사된 스냅샷 사용**: 이제 목적지 리전에는 "B"라는 KMS 키로 암호화된 스냅샷이 있습니다. 이 스냅샷을 기반으로 EBS 볼륨을 생성하면, 해당 볼륨 역시 "B"라는 KMS 키로 암호화됩니다.

<br>

> 스냅샷을 다른 리전으로 복사하는 과정 중에 데이터는 `임시적으로 복호화`되었다가 목적지 리전의 KMS 키로 다시 암호화되는 과정을 거칩니다. 

> **AWS 내부 네트워크의 보안:** 위의 복호화 및 재암호화 과정은 `AWS 내부 네트워크`를 통해 이루어지므로 데이터의 보안이 유지됩니다.


<br>

## KMS Multi-Region Key의 등장
- AWS는 멀티 리전 키의 개념을 도입하여 `같은 키를 여러 리전에서 사용`할 수 있게 했습니다.
- 이 방식을 사용하면 위와 같은 복잡한 재암호화 과정 없이 데이터를 여러 리전에서 보호할 수 있습니다.
- 같은 키라고는 하지만 `하나의 KMS키를 글로벌하게 사용할 수 있는 것이 아님` -> Primary가 하나 있고 여러 Replicas가 있는 것과 동일(각 리전에 있는 KMS키를 사용하는 것 + 각 리전 키는 `각각 독립적`으로 관리됨)
- 보안상으로는 단일 리전에 제한되어 관리하는 것이 선호되기 때문에 특정 경우를 제외하고는 Multi-Region Key를 권장하지 않음
      - 사용 사례 : 글로벌 클라이언트 암호화 (ex. Aurora 멀티 클러스터 암호화)
