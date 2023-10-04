Socket 은 File 이다.

File I/O 를 한다

File 관점으로 본다면 Read / Write 이지만
Socket 관점에서는 Send / Receive 라고 한다.

Socket에서는 큰 파일을 Block 단위로 잘게잘게 쪼개서 전달하게 된다.

Stream을 쪼개서 전달하는 것이다.

Stream은 시작은 있지만 끝은 언제인지 알 수 없다.