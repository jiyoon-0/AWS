## VPC
- Public Subnet
  - Internet GW를 통하여 외부 인터넷 구간과 통신
  - EC2 -> 가상 라우터 -> 라우팅 테이블(IGW) -> 인터넷 구간
  - 외부 -> Public IP를 목적지로 EC2 접속
- Private Subnet
  - NAT GW를 통하여 외부 인터넷 구간과 통신
  - Private Subnet의 EC2 <-> 외부 통신 가능
  - Private Subnet이 NATGW 통하여 인터넷으로 나가지만 NATGW로 Private Subnet에 들어올 수는 없음(아웃바운드만)
  - NAT GW는 Public Subnet에 위치, Public RT 적용
  - Private EC2 -> 가상 라우터 -> 라우팅 테이블(NAT GW) -> NAT GW(Private IP->Public IP전환) -> IGW  
  *) 사용자는 NAT GW에서 변환한 Public IP로 전달 받음
