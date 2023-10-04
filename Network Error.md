네트워크 에러는 크게 4가지 정도로 볼 수 있다.

-  Loss (유실)
	- 이는 TCP 단에서 데이터를 유실하는 것을 말한다.
- ReTransmission + Ack duplication
	- 이는 받은 데이터에 대한 응답이 늦어져 클라이언트 측에서는 새로운 전송을 하고
	- 서버 측에서는 Ack를 다중으로 전송하는 것을 의미 한다.
	- 네트워크 속도의 문제일까?
- Out of Order
	- 데이터가 뒤죽박죽으로 섞여 목적지에 도착되는 것을 말한다.
- Zero window
	- 데이터를 전달하게 되면 전달을 받은 쪽에서는 Ack에 현재 Buffer에 남아있는 여유 공간을 실어서 응답을 보내는데 이 응답이 Zero 인 경우에 발생하게 된다. 여유공간이 없는 경우 보낼 수 가 없다.

[TCP Out-of-order 에 관한 글](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=sokmpower&logNo=120066435389)