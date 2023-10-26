## AWS SNS의 Dead Letter Queue

Amazon SNS (Simple Notification Service)는 발행/구독 모델을 기반으로 하는 통보 서비스입니다. 
Amazon SNS에서 메시지가 구독자에게 성공적으로 전달되지 않을 경우, 이러한 실패한 메시지를 처리하기 위해 "데드 레터 대기열" (DLQ, Dead Letter Queue)이라는 기능을 제공합니다.

1. **목적**: 데드 레터 대기열은 SNS 메시지가 구독자에게 성공적으로 전달되지 않았을 때 해당 메시지를 잡아내는 역할을 합니다.
   
2. **Amazon SQS와의 통합**: 데드 레터 대기열은 `Amazon SQS (Simple Queue Service) 대기열`로 구성됩니다. 따라서 SNS에서 메시지가 성공적으로 전달되지 않을 경우 해당 메시지는 SQS의 데드 레터 대기열로 이동됩니다.
   
3. **분석 및 디버깅**: 데드 레터 대기열에 쌓인 `메시지를 분석`하여 메시지 전달 실패의 원인을 파악하고 문제를 해결할 수 있습니다.
