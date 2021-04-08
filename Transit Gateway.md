## TGW(Transit Gateway)  
- 허브 및 스포크 방식의 네트워크 토폴로지 구축 기능  
- 여러 AWS 계정 및 DC, 원격 게이트웨이를 TGW에 연결하고 제어 가능  
- 여러 계정 간에 AWS 리소스를 공유할 수 있도록 AWS Resource Access Manager(RAM) 사용  
*) 리소스에 엑세스할 수 있는 다른 AWS 계정의 목록을 지정  
- TGW를 방화벽 또는 IPS에 연결하여 모든 송수신 트래픽을 처리하는 단일 VPC 구성 가능  
  
1) 관리형 계정에서 TGW 생성  
- 자동으로 요청을 수락하는 옵션  
2) Resource Access Manager  
- TGW로 공유할 계정을 등록(OU나 조직으로 가능)  
https://www.slideshare.net/awskorea/aws-transit-gateway-multivpc-aws-aws-summit-seoul-2019
