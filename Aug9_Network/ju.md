# 네트워크 - TCP&UDP, HTTP&HTTPS

### Protocol
컴퓨터 내부 또는 컴퓨터 사이에서 데이터의 교환 방식을 정의하는 규칙 체계

### 소켓과 패킷이란 무엇인가?
https://babbab2.tistory.com/9
https://chung-develop.tistory.com/82

### OSI 7 layer
OSI 모형 (Open Systems Interconnection Reference Model)은 국제 표준화 기구(ISO)에서 개발한 모델로, 컴퓨터 네트워크 프로토콜 디자인과 통신을 계층으로 나누어 설명한 것이다. 일반적으로 OSI 7 계층 모형이라고 한다. 이 모델은 프로토콜을 기능별로 나눈 것으로 각 계층은 하위 계층의 기능만을 이용하고, 상위 계층에게 기능을 제공한다.

#### 계층 구조
>피지컬 계층(L1), 데이터 링크 계층(L2), 네트워크 계층(L3), 트랜스포트 계층(L4), 세션 계층(L5), 프리젠테이션 계층(L6), 애플리케이션 계층(L7)

> 하위층 L1 L2 L3 L4 (Data Flow Layer)
데이터를 상대방에게 잘 전달하는 역할

> 상위층 L5 L6 L7 (Application Layer)

<img src="https://t1.daumcdn.net/cfile/blog/990F804A5E129F0F1D" width="300px">

[OS 7 계층](https://blog.daum.net/hellstar/25)
[OS 7 layer 쉽게 이해하기](https://aws-hyoh.tistory.com/entry/OSI-7-Layer-%EC%89%BD%EA%B2%8C-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0)

### TCP / IP 모델
#### 계층 구조
>  네트워크 엑세스, 인터넷, 트랜스포트 계층, 어플리케이션 계층

[TCP/ IP](https://brunch.co.kr/@wangho/6)

TCP/IP는 패킷 통신 방식의 인터넷 프로토콜인 IP와 전송 조절 프로토콜인 TCP로 이루어져 있다.

### Transport Layer - 프로토콜 TCP & UDP
OSI 7 계층의 전송 계층에 해당
통신 노드 간의 연결을 제어하고, 신뢰성 있는 데이터 전송을 담당

### TCP(Transmission Control Protocol)
- 연결형 서비스를 지원하는 전송계층 프로토콜
- 인터넷 환경에서 기본으로 사용
- 호스트간 신뢰성 있는 데이터 전달과 흐름제어 및 혼잡제어 등을 제공하는 전송계층

- 특징 
    - 데이터의 경계를 구분 안함
    - 신뢰성 있는 데이터 전송
    - 데이터 전송 순서의 보장
    - 데이터의 수신 여부 확인
    - 패킷을 관리할 필요 없음
    - UDP보다 전송속도가 느림

### UDP(User Datagram Protocol)
- 비연결형 서비스를 지원하는 전송계층 프로토콜
- 사용자 데이터그램형 프로토콜
- 인터넷상에서 서로 정보를 주고받을 때 정보를 보낸다는 신호나 받는다는 신호 절차를 거치지 않고, 보내는 쪽에서 일방적으로 데이터를 전달하는 통신 프로토콜
- 보내는 쪽에서는 받는 쪽이 데이터를 받았는지 받지 않았는지 확인할 수 없고, 또 확인할 필요도 없도록 만들어진 프로토콜

- 특징
    - 데이터의 경계를 구분함
    - 신뢰성 없는 데이터 전송
    - 데이터의 전송 순서가 바뀔 수 있음
    - 데이터의 수신 여부를 확인 안함
    - 패킷을 관리해야 함
    - TCP보다 전송속도가 빠름


[TCP와 UDP의 특징과 차이점](https://odeyou.tistory.com/109)
[TCP UDP 강의](https://www.inflearn.com/course/http-%EC%9B%B9-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC/unit/61354)


## HTTP(Hyper Text Transfer Protocol)
서버/클라이언트 모델을 따라 데이터를 주고 받기 위한 프로토콜이다. 1989년 팀 버너스리에 의해 처음 설계되었으며 WWW(World-Wide-Web) 기반에서 세계적인 정보를 공유하는데 큰 역할을 하였다.

80번 포트를 사용한다.

Application level의 protocol로 TCP/ IP 위에서 작동한다.

- 문제점
서버에서 브라우저로 전송되는 정보가 암호화되지 않는다

## HTTPS(Hyper Text Transfer Protocol Secure)
HTTP에 암호화가 추가된 프로토콜이다. 네트워크상에서 중간에 제 3자가 정보를 볼 수 없도록 암호화를 지원하고 있다.

443번 포트를 사용한다.

- SSL(보안 소켓 계층)또는 TLS 프로토콜을 사용하여 서버와 브라우저 사이에 안전하게 암호화된 연결을 생성, 민감한 정보 도난 방지



[HTTP와 HTTPS의 차이](https://blog.wishket.com/http-%EA%B7%B8%EB%A6%AC%EA%B3%A0-https%EC%9D%98-%EC%9D%B4%ED%95%B4/)
[HTTP와 HTTPS](https://mangkyu.tistory.com/98)