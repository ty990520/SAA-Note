## 오리진 액세스 제어 & 오리진 액세스 ID

1. **오리진 액세스 제어 (Origin Access Control, OAC)**
   - OAC는 CloudFront에서 콘텐츠를 보호하고 S3 버킷에 대한 접근을 제한하기 위한 방법 중 하나입니다.
   - S3 버킷의 `정책`을 사용하여 CloudFront를 통해서만 콘텐츠에 접근할 수 있도록 설정할 수 있습니다.

2. **오리진 액세스 ID (Origin Access Identity, OAI)**
   - OAI는 CloudFront가 S3 버킷에 접근할 때 사용하는 특별한 CloudFront `사용자`를 의미합니다.
   - 사용자는 OAI를 생성하여 CloudFront 배포에 연결할 수 있으며, 이를 통해 CloudFront를 통해서만 S3 버킷의 콘텐츠에 접근할 수 있도록 설정할 수 있습니다.
   - S3 버킷 정책에 OAI를 사용하여 CloudFront를 통한 접근만을 허용하도록 설정할 수 있습니다.

<br>

**공통점**
- 둘 다 `Amazon CloudFront`를 사용하여 `S3 버킷`의 콘텐츠에 대한 `접근을 제어하고 보호`하는데 사용됩니다.
- 둘 다 S3 버킷에 대한 `직접적인 접근을 제한`하고 CloudFront를 통한 접근만을 허용하도록 설정하는 방법입니다.

**차이점**
- OAC (Origin Access Control)는 CloudFront에서 콘텐츠를 보호하기 위한 새로운 방법으로, S3 버킷 정책을 사용하여 CloudFront를 통한 접근만을 허용하도록 설정할 수 있습니다.
- OAI (Origin Access Identity)는 CloudFront가 S3 버킷에 접근할 때 사용하는 특별한 CloudFront 사용자를 의미하며, OAI를 생성하여 CloudFront 배포에 연결함으로써 CloudFront를 통한 접근만을 허용하도록 설정할 수 있습니다.
- 간단히 말하자면, OAC는 S3 버킷 정책을 사용하는 반면, OAI는 CloudFront 사용자를 사용하여 접근을 제어합니다.
