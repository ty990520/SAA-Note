## Amazon EC2 Auto Scaling에서 사용할 수 있는 다양한 정책 유형

1. **대상 추적 정책 (Target Tracking Scaling Policy):**
   - 사용자가 `설정한 목표 값`을 유지하도록 Auto Scaling 그룹을 자동으로 조정합니다.
   - 예: CPU 사용률을 40%로 유지하기 위해 인스턴스를 추가하거나 제거합니다.

2. **간단한/단계별 확장 정책 (Simple/Step Scaling Policy):**
   - `CloudWatch 경보`를 기반으로 Auto Scaling 그룹의 크기를 조정합니다.
   - 조건을 충족할 때마다 지정된 수의 인스턴스를 추가하거나 제거 (대상 추적 정책과의 차이점)
   - 예: CPU 사용률이 70%를 초과하면 인스턴스를 2개 추가합니다.

3. **예약된 확장 정책 (Scheduled Scaling Policy):**
   - `예약된 시간`에 Auto Scaling 그룹의 크기를 조정합니다.
   - 예: 특정 시간에 트래픽이 증가할 것으로 예상되므로 인스턴스를 추가합니다.

4. **예측 확장 정책 (Predictive Scaling Policy):**
   - 기계 학습 모델을 사용하여 `트래픽 패턴을 예측`하고 그에 따라 Auto Scaling 그룹의 크기를 조정합니다.
   - 예: 트래픽 패턴을 분석하여 트래픽이 증가하기 전에 인스턴스를 추가합니다.

