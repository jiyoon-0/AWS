##AWS Client VPN(SSL VPN)
![Client AWS](https://user-images.githubusercontent.com/79958913/111418416-0a3c4e80-872b-11eb-8d16-cb744bea01c2.PNG)
- 배경 : 외부 업체에게 그룹사 VPN 발급 지양, 기존에는 그룹사 SSL VPN -> SGTray로 접속
- 접속 방식 : AWS Client VPN -> SSH 접속
- 설정 방법 
  1) 인증 및 권한 부여
  - 상호인증(ACM 인증서)
  - 인증서는 인증기관(CA)에서 발행한 디지털 형태의 ID 인증서
  - 서버는 클라이언트 인증서를 사용하여 엔드포인트에 연결하려고 시도하는 클라이언트를 인증
  - 하나의 서버 인증서와 클라이언트 인증서 생성
  - ACM에 서버 인증서 업로드 및 CA 지정
  2) SG 및 네트워크 기반 권한 부여
  - Associations에서 VPC, Subnet 설정
  - VPN SG 생성 필요
  - Authorization에서 사용자가 엑세스하려는 네트워크 주소(VPC CIDR) 표기
  4) 라우팅
  - 분할 터널 : 목적지가 AWS인 트래픽만을 VPN 터널을 통과하도록 지정하여 트래픽 라우팅 최적화
  6) 정책 설정
  - VPN SG 아웃바운드에 Subnet 대역 ALL TCP와 ICMP 오픈
  - VPN Endpoint가 있는 Subnet 대역을 서버 SG에서 오픈
  7) 확인
  - 테더링으로 VPN 연결 후 ping 테스트
  - 참고문서 : https://docs.aws.amazon.com/ko_kr/vpn/latest/clientvpn-admin/cvpn-working-endpoints.html#cvpn-working-endpoint-create
