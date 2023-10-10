## Organizaions

- 글로벌 서비스
- 다수의 AWS 계정을 동시에 관리할 수 있음
- 조직을 생성하면 조직의 메인 계정이 management account가 됨 (나머지는 member account라고 부름)
- member account는 한 Organizaion에만 소속됨
- 모든 계정의 비용을 통합 결제할 수 있음 (+할인혜택 제공)
- 계정 간에 예약 인스턴스와 Savings Plans 할인이 공유됨 -> 비용 절감 효율적
- 계정을 자동으로 생성하는 api를 제공하기 때문에 다수의 계정을 편리하게 생성 가능

<br>

# 작동 원리
![Organizaions](https://private-user-images.githubusercontent.com/48792230/273760333-02c4c7d5-f6bc-416c-a166-b7a3ce3b35ea.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTEiLCJleHAiOjE2OTY5MDYxNjgsIm5iZiI6MTY5NjkwNTg2OCwicGF0aCI6Ii80ODc5MjIzMC8yNzM3NjAzMzMtMDJjNGM3ZDUtZjZiYy00MTZjLWExNjYtYjdhM2NlM2IzNWVhLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFJV05KWUFYNENTVkVINTNBJTJGMjAyMzEwMTAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjMxMDEwVDAyNDQyOFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTAyNmJiZDNkZGI0ZmJlNzE4MmU5MmZkM2VlMWFlNjAyODE3ZjFhNjZiYjYxYTY2ZGQzYmMxN2YwNjkxNDk4ZmImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.kMBEXj7UWcUlHtvwWfDsqTzO0WC85QuypRUeqeXWuao)
- Root Organization Unit (OU) : 전체 계정에서 제일 외곽에 위치
- 내부에 management account가 포함됨
- 서브 OU 생성 가능
- 테두리라고 생각하면 될 듯

<br>

# 장점
- 다수의 계정을 통합 관리하므로 다수의 VPC를 가진 단일 계정에 비해 보안이 우수함
    - 계정의 보안이 VPC의 보안보다 더 우수하기 때문 (계정이 더 독립적) 
- billing 목적을 위한 태그 기능을 사용할 수 있음
- 한 번에 모든 계정에 대해 CloudTrail을 활성화해서 모든 로그를 중앙 S3 계정으로 전송할 수 있음 (모니터링 편리)
- CloudWatch Logs를 중앙 로깅 계정으로 전송할 수 있음
- 역할을 분리할 수 있어서 관리 측면에서 우수
- **특히 보안 측면에서 우수함**
    - Service Control Policies(SCP)를 정의할 수 있음
      - 특정 OU 또는 계정에 적용되는 IAM 정책
      - 해당 사용자와 역할 모두가 계정 내에서 할 수 있는 일을 제한할 수 있음
      - SCP는 management account에는 적용되지 않음 (설정해봤자 적용 안됨)
      - IAM처럼 기본적으로 아무것도 허용하지 않음 (구체적인 허용 항목을 설정해야함)
      - 아래 이미지 참고

![SCP](https://private-user-images.githubusercontent.com/48792230/273764946-ce9fc537-1207-48ed-955b-ab7e3bca600e.jpg?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTEiLCJleHAiOjE2OTY5MDc4OTYsIm5iZiI6MTY5NjkwNzU5NiwicGF0aCI6Ii80ODc5MjIzMC8yNzM3NjQ5NDYtY2U5ZmM1MzctMTIwNy00OGVkLTk1NWItYWI3ZTNiY2E2MDBlLmpwZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFJV05KWUFYNENTVkVINTNBJTJGMjAyMzEwMTAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjMxMDEwVDAzMTMxNlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWE5M2ZkNDAwM2M3MWEzZWZmNjRkNWFjMDM4MDFjMDA5ODNhODZiMmZiZDUyM2U5YWZlYTdhN2E1NjgyNDBlZjImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.R8seSNqUF9kkFaWV6IV9eMRW8wYzbPe4IxJl4Zr4kOU)
