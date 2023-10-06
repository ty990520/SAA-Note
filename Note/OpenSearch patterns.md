## OpenSearch patterns

### 1. OpenSearch patterns with DynamoDB
![DynamoDB](https://private-user-images.githubusercontent.com/48792230/273098162-b59c0f79-cbd7-4879-8107-d5b635225c63.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTEiLCJleHAiOjE2OTY1NjQwNzIsIm5iZiI6MTY5NjU2Mzc3MiwicGF0aCI6Ii80ODc5MjIzMC8yNzMwOTgxNjItYjU5YzBmNzktY2JkNy00ODc5LTgxMDctZDViNjM1MjI1YzYzLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFJV05KWUFYNENTVkVINTNBJTJGMjAyMzEwMDYlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjMxMDA2VDAzNDI1MlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTU0N2IzN2VlYWVmYWU4MDcxOWY4MDcyYzJlZWIwYTJlMDRkYmM0YTY0ZTQ2Y2Y5YWRhMDIyNjNmMTA0OGUzZmImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.wshVzWCxKjduncdmzkIqJJmMlRUW0oCl4U4m5WLGxTk)

   - DynamoDB에 데이터를 삽입, 삭제, 업데이트.
   - 모든 데이터 업데이트 스트림을 DynamoDB Stream에 전송.
   - 람다 함수가 DynamoDB Stream을 감지하여 Amazon OpenSearch에 실시간으로 데이터 삽입.
   - 애플리케이션은 OpenSearch를 통해 항목 이름의 부분 검색이나 항목 ID 검색 가능.
   - 항목 ID를 통해 실제 데이터는 DynamoDB에서 가져옴.
   - 여기서 OpenSearch는 검색 기능 제공, 실제 데이터 출처는 DynamoDB.

---

### 2. OpenSearch patterns with CloudWatch Logs
![CloudWatch Logs](https://private-user-images.githubusercontent.com/48792230/273098253-73912c2b-4348-4a2d-889f-e97f1707ce79.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTEiLCJleHAiOjE2OTY1NjUxMTQsIm5iZiI6MTY5NjU2NDgxNCwicGF0aCI6Ii80ODc5MjIzMC8yNzMwOTgyNTMtNzM5MTJjMmItNDM0OC00YTJkLTg4OWYtZTk3ZjE3MDdjZTc5LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFJV05KWUFYNENTVkVINTNBJTJGMjAyMzEwMDYlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjMxMDA2VDA0MDAxNFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTY0YjY1OTgzYTVhZTViODhhNzQxZTM2OGM4NTg5MDM3ZTg1NWFjZmYwNTJkZGY3MGEzNmVjMGQ5ZWU5MWY0NTImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.rL_w_42xP7U3GIxbDwIs8eopBHIhhwspYTK0rpmjki8)
   - CloudWatch Logs Subscription Filter를 사용하여 데이터를 람다 함수에 실시간 전송.
   - 람다 함수는 해당 데이터를 OpenSearch로 전송.
   - Kinesis Data Firehose를 이용하여 Subscription Filter로부터 데이터 읽기 가능.
   - Kinesis Data Firehose를 통해 거의 실시간으로 OpenSearch에 데이터 삽입.

---

### 3. OpenSearch patterns with Kinesis Data Streams
![Kinesis](https://private-user-images.githubusercontent.com/48792230/273098319-6fee3220-0071-4b28-b913-e0442f33fbe3.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTEiLCJleHAiOjE2OTY1NjUxMTQsIm5iZiI6MTY5NjU2NDgxNCwicGF0aCI6Ii80ODc5MjIzMC8yNzMwOTgzMTktNmZlZTMyMjAtMDA3MS00YjI4LWI5MTMtZTA0NDJmMzNmYmUzLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFJV05KWUFYNENTVkVINTNBJTJGMjAyMzEwMDYlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjMxMDA2VDA0MDAxNFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTBiMGIwOTExMDFjODc3YjM4MWE3ZDRmNGMyYzVmZDZhOWE2NDhmY2VjNGE2Y2Q2N2FjNjBmOGEwMjY5Y2NlNzkmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.WtPwSRN373W6U5it6U64rpHSXT4BJJYMLJ1tssypyhQ)
   - Kinesis Data Streams를 Amazon OpenSearch에 전송하기 위한 두 가지 전략 사용
   - **a. Kinesis Data Firehose 사용**
      - 근 실시간 타입의 서비스.
      - 람다 함수를 이용해 데이터 변환 가능.
      - 변환된 데이터를 Amazon OpenSearch로 전송
   - **b. 람다 함수를 이용한 실시간 스트림 읽기**
      - Kinesis Data Streams에서 실시간으로 데이터 스트림을 읽는 람다 함수 생성.
      - 커스텀 코드를 작성하여, 람다 함수가 Amazon OpenSearch에 실시간으로 데이터 기록.

