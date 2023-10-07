
아이피 구조 
8bit * 4 = 32bit

한칸에 8bit의 표현방식으로 인해 0~255 의 숫자 제한을 가짐.

ex) 192.168.0.2

앞에서 3개는 Network Id

나머지 뒤에 1개는 Host Id 이다.

```
192.168.0 -> Network Id
2 -> Host Id
```
Network Id는 동네
Host Id는 주거지 정도로 이해하면 된다.

IPv4의 데이터 형식은

`HEADER | PAYLOAD`

로 이루어 진다.

HAADER에는 IP, src, dst 등이 들어가있고 payload에는 data가 적재되있다.

기본적으로 L3 단계의 MTU는 1500Bytes 정도이다.

예외로 VPN을 사용하는 경우 1400Bytes 인 경우가 있다.

[[Subnet mask]]와 [[CIDR]]

[[TTL]] 이 존재한다.

