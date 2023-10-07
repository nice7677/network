
# Address Resolution Protocol

[[IP]] 주소를 [[MAC]] 주소와 매칭 시키기 위한 프로토콜이다.

MAC주소는 거의 변하지 않기 때문에 캐시를 걸어 사용할 수 있다.

ARP Request 또한 DHCP의 요청과 마찬가지로 [[BroadCast]]를 요청해 다른 서버와 연결된 Gateway에 접근하여 MAC주소의 위치를 알아낸다. 방식이 복잡하고 효율이 떨어지기에 한번 요청된 ARP는 캐시를 걸어 사용한다.
