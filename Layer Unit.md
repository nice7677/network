[[L1]], [[L2]] => Frame (H/W)
[[L3]] => Packet (IP)
	Packet 의 최대 크기 MTU는 1500Byte이다.
[[L4]] => Segment (TCP)
	L3위에있는 L4는 MSS라는 데이터의 크기를 가지는데 이는 특별한 경우가 아닌이상 1460Byte이다.
	L3위에 있기때문에 L3의 최대 데이터 크기인 1500Byte보다 클 수 없다.
[[L5]] => Stream (Socket)
	Socket의 데이터 단위인 Stream은 데이터 덩어리 그 자체이다. 하위 레이어 에서 사이즈에 맞게 큰 Stream 데이터 덩어리를 쪼개서 전달한다.