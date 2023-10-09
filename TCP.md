# 연결 개념

1. Connection
2. Session

연결이란 상태(전이)라는 개념을 동반함.

TCP의 데이터 단위는 `Segment`라고 함

![](https://media.geeksforgeeks.org/wp-content/uploads/TCPSegmentHeader-1.png)

위의 그림과 같은 구조를 가진 데이터를 가지고있음.

TCP의 주체는 `Client` 임. 연결하는 것도, 끊는 것도 Client여야함.

만약 Server 에서 끊는 신호가 오고 Client에서 Time wait 가 발생하면 이는 Server 쪽에 문제가 생긴것.

Segment에서 Sequence Number는 랜덤임.

그리고 랜덤인 값에 payload의 값이 추가 됨.

시퀀스 넘버 + Date length 가 됨.

정책 교환. MSS (Maximum Segment Size) 가 주임.

# 3way handshaking

3번 손 흔들기는 Client에서 Server쪽으로 연결을 하기 위한 흔들기임.

3번 손 흔들기는 그냥 말그대로 손을 3번 흔드는거다.

Client쪽에서 Server로 손을 흔들면
Server에서 Client로 손을 흔들고
Client에서 응답으로 Server에 손을 흔든다.

![TCP 3-Way Handshake Process - GeeksforGeeks](https://media.geeksforgeeks.org/wp-content/uploads/handshake-1.png)
- **1단계(SYN):** 첫 번째 단계에서 클라이언트는 서버와 연결을 설정하려고 SYN(Synchronize Sequence Number)이 포함된 세그먼트를 보냅니다. 이 세그먼트는 클라이언트가 통신을 시작할 가능성이 있고 어떤 순서로 서버에 알리는 것입니다. 세그먼트를 시작하는 번호
- **2단계(SYN + ACK):** 서버는 SYN-ACK 신호 비트 세트를 사용하여 클라이언트 요청에 응답합니다. 승인(ACK)은 수신한 세그먼트의 응답을 나타내고 SYN은 세그먼트를 시작할 가능성이 있는 시퀀스 번호를 나타냅니다.
- **3단계(ACK):** 마지막 부분에서 클라이언트는 서버의 응답을 확인하고 둘 다 실제 데이터 전송을 시작할 안정적인 연결을 설정합니다.

# 4way handshaking

4번 손흔들기는 Client쪽에서 Server쪽으로 연결을 끊기 위한 흔들기임.

4번 손 흔들기는 그냥 말그대로 손을 4번 흔드는거다.

![The Four-Way Handshake Process](https://media.geeksforgeeks.org/wp-content/uploads/20220406111342/TheFourWayHandshakeProcess.jpg)

클라이언트 쪽에서 Fin을 보내고 서버에서 응답을 보내고 

다시한번 서버쪽에서 Fin을 보내고 클라이언트에서 응답을 보내고 끊기는 것.

# 3,4 손흔들기

위에 설명과 그림에서 볼 수 있듯이 주체는 클라이언트임.

서버쪽에서 먼저 Fin이 온다면 무언가 서버에서 이상이 생긴것.

# TCP 연결이라는 착각

TCP는 L1 에서 연결이 끊기더라도 연결이 유지 되어 있음.

기본으로 재전송 타이머 근사 값은 3초 지만 OS단에서 1초 미만으로 연결을 끊어 버림.

L1 단계에서 연결이 끊긴 것을 `충격`이라고 함.

이 충격을 방지 하기 위해 Buffer에 미리 다음의 여유분들을 채워 놓음.

이로써 충격을 방지함.

만약 연결이 진짜로 끊긴다면 보통 최대 5회 재전송을 시도하고 모두 실패시 오류를 발생한다.

`연결은 사실 Ent-Point의 주관적 판단에 불과하다.`