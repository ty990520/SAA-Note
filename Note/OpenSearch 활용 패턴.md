## OpenSearch 활용 패턴

<br>

### 1. **DynamoDB와의 연계**
![DynamoDB](https://private-user-images.githubusercontent.com/48792230/273098162-b59c0f79-cbd7-4879-8107-d5b635225c63.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTEiLCJleHAiOjE2OTY1NjQwNzIsIm5iZiI6MTY5NjU2Mzc3MiwicGF0aCI6Ii80ODc5MjIzMC8yNzMwOTgxNjItYjU5YzBmNzktY2JkNy00ODc5LTgxMDctZDViNjM1MjI1YzYzLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFJV05KWUFYNENTVkVINTNBJTJGMjAyMzEwMDYlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjMxMDA2VDAzNDI1MlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTU0N2IzN2VlYWVmYWU4MDcxOWY4MDcyYzJlZWIwYTJlMDRkYmM0YTY0ZTQ2Y2Y5YWRhMDIyNjNmMTA0OGUzZmImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.wshVzWCxKjduncdmzkIqJJmMlRUW0oCl4U4m5WLGxTk)
- **작업**: DynamoDB에서 데이터의 삽입, 삭제, 업데이트가 이루어집니다.
- **데이터 흐름**: 모든 데이터 변경 사항(스트림)은 DynamoDB Stream에 보내집니다.
- **중개자**: 람다 함수가 이 스트림을 감지하고, 해당 데이터를 Amazon OpenSearch로 전송합니다.
- **기능**: 이로 인해, 애플리케이션은 OpenSearch를 통해 데이터를 효과적으로 검색할 수 있게 됩니다. 실제 데이터는 DynamoDB에 남아 있습니다.

<br>

### 2. **CloudWatch Logs와의 연계**
![CloudWatch Logs](https://private-user-images.githubusercontent.com/48792230/273098253-73912c2b-4348-4a2d-889f-e97f1707ce79.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTEiLCJleHAiOjE2OTY1NjUxMTQsIm5iZiI6MTY5NjU2NDgxNCwicGF0aCI6Ii80ODc5MjIzMC8yNzMwOTgyNTMtNzM5MTJjMmItNDM0OC00YTJkLTg4OWYtZTk3ZjE3MDdjZTc5LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFJV05KWUFYNENTVkVINTNBJTJGMjAyMzEwMDYlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjMxMDA2VDA0MDAxNFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTY0YjY1OTgzYTVhZTViODhhNzQxZTM2OGM4NTg5MDM3ZTg1NWFjZmYwNTJkZGY3MGEzNmVjMGQ5ZWU5MWY0NTImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.rL_w_42xP7U3GIxbDwIs8eopBHIhhwspYTK0rpmjki8)
- **로그 전송**: CloudWatch Logs에서 나온 로그 데이터가 람다 함수로 실시간으로 전송됩니다.
- **데이터 처리 및 전송**: 람다 함수가 데이터를 처리하고 OpenSearch로 보냅니다.
- **추가적인 옵션**: Kinesis Data Firehose를 사용하여 데이터를 거의 실시간으로 OpenSearch에 삽입할 수도 있습니다.

<br>

### 3. **Kinesis Data Streams와의 연계**
![Kinesis](https://private-user-images.githubusercontent.com/48792230/273098319-6fee3220-0071-4b28-b913-e0442f33fbe3.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTEiLCJleHAiOjE2OTY1NjUxMTQsIm5iZiI6MTY5NjU2NDgxNCwicGF0aCI6Ii80ODc5MjIzMC8yNzMwOTgzMTktNmZlZTMyMjAtMDA3MS00YjI4LWI5MTMtZTA0NDJmMzNmYmUzLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFJV05KWUFYNENTVkVINTNBJTJGMjAyMzEwMDYlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjMxMDA2VDA0MDAxNFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTBiMGIwOTExMDFjODc3YjM4MWE3ZDRmNGMyYzVmZDZhOWE2NDhmY2VjNGE2Y2Q2N2FjNjBmOGEwMjY5Y2NlNzkmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.WtPwSRN373W6U5it6U64rpHSXT4BJJYMLJ1tssypyhQ)
- **전략 1: Kinesis Data Firehose 사용**
  - 이 방식은 근 실시간 서비스입니다. 람다 함수를 통해 데이터를 변환한 후 OpenSearch로 보냅니다.
- **전략 2: 람다 함수를 이용한 실시간 스트림 읽기**
  - Kinesis Data Streams에서 데이터 스트림을 실시간으로 읽어, 커스텀 코드를 사용하여 OpenSearch에 데이터를 기록합니다.

