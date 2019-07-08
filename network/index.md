# 네트워크 용어정리.

커뮤니케이션을 위한 네트워크 용어정리<br>
정말 단순한 추상화레벨부터 익히자.


## 패킷(Pakit)
패킷이란 전송하는 데이터의 최소 단위

 
## TCP/IP
		-Transmission Control Protocol(전송 제어 규약)
		-Internet Protocol(인터넷 규약)
		-TCP와 IP는 데이터가 어떻게 웹을 건나 여행하는지 정의하는 통신 규약입니다.
		-이것은 주문하고 상점에 가고 또 여러분이 상품을 살 수 있게 해주는 운송장치와 같습니다.
		-우리 예시에서 이것은 차 또는 자전거로 비유 할 수 있습니다.
	

## TCP (Three way handshaking)
TCP(Transfer Control Protocol)는 대용량의 데이터를 보내기 쉽게 작게 분해하여 상대에게 보내고, 정확하게 도착했는지 확인하는 역할을 담당한다.<br>
 TCP는 상대에게 확실하게 데이터를 보내기 위해 "쓰리웨이 핸드셰이킹(three way handshaking)"이라는 방법을 사용하고 있는데 이 방법은 패킷을 보내고 나서 바로 끝내는 것이 아니라, 보내졌는지 여부를 상대에게 확인하러 간다.<br>
  이것은 'SYN'와 'ACK'라는 TCP 플래그를 사용한다.<br>
   송신측에서는 최초 'SYN'플래그로 상대에게 접속함과 동시에 패킷을 보내고, 수신측에서는 'SYN/ACK' 플래그로 송신측에 접속함과 동시에 패킷을 수신한 사실을 전한다.<br>
    마지막으로 송신측이 'ACK' 플래그를 보내 패킷 교환이 완료되었음을 전한다. 


## TCP/IP 계층화 
-TCP/IP는 '애플리케이션 계층', '트랜스포트 계층(TCP)', '네트워크 계층(IP)', '링크 계층' 이렇게 총 4계층으로 나뉘어 있다. <br>
계층화의 메리트는 인터넷이 하나의 프로토콜로 되어 있다면 어디선가 사양이 변경되었을 때 전체를 바꾸지 않으면 안되지만, 계층화되어 있으면 사양이 변경된 해당 계층만 바꾸면 됩니다.

## IP, MAC
-IP(Internet Protocl)의 역할은 개개의 패킷을 상대방에게 전달하는 것. 상대방에게 전달하기까지 여러 요소가 필요한데 그 중에서도 IP와 MAC(Media Access Control Address)라는 요소가 중요하다.<br>
IP주소는 각 노드에 부여된 주소를 가리키고 MAC 주소는 각 네트워크 카드에 할당된 고유의 주소이다. IP주소는 변경 가능하지만 기본적으로 MAC 주소는 변경 할 수 없다.


## HTTP, STATLESS PROTOCOL
-HTTP는 상태를 계속 유지하지 않는 스테이트리스(stateless)프로토콜로 리퀘스트와 리스폰스를 교환하는 동안에 상태를 관리하지 않는다. HTTP에서는 새로운 리퀘스트가 보내질 때 마다 새로운 리스폰스가 생성된다.<br>
 프로토콜로서는 과거의 리퀘스트나 리스폰스 정보를 전혀 가지고 있지 않다. 이는 많은 데이터를 매우 빠르고 확실하게 처리하는 범위성(scalability)을 확보하기 위해서 이와 같이 간단하게 설계되어 있는 것이다. 

## 쿠키
쿠키는 리퀘스트와 리스폰스에 쿠키 정보를 추가해서 클라이언트의 상태를 파악하기 위한 시스템이다.



## 프록시 서버(Proxy Server)
![](/resource/img/ProxyServer.png)
서버와 클라이언트의 양쪽 역할을 하는 중계 프로그램으로, 클라이언트로부터의 리퀘스트를 서버에 전송하고, 서버로부터의 리스폰스를 클라이언트에 전송한다.<br>

클라이언트 <-> 프록시 서버 <-> 오리진 서버(Origin Server, 리소스 본체를 가진 서버)<br>
프록시 서버를 사용하는 이유는 캐시를 사용해서 네트워크 대역 등을 효율적으로 사용하는 것과 조직 내에 특정 웹 사이트에 대한 액세스 제한, 액세스 로그를 획득하는 정책을 지키려는 목적으로 사용하는 경우가 있다.



## 프록시 사용 방법 2가지

#### 1.캐싱 프록시(Cashing Proxy)
 프록시에 다시 같은 리소스에 리퀘스트가 온 겨우, 오리진 서버로부터 리소스를 획득하는 것이 아니라 캐시를 리스폰스로서 되돌려 주는 타입의 프록시

#### 2.투명 프록시(Transparent Proxy)
 리퀘스트와 리스폰스를 중계할 때 메시지 변경을 하지 않는 타입의 프록시, 반대로 메시지에 변경을 가하는 타입의 프록시를 비투과 프록시라고 한다.

## 프록시 서버의 종류

#### 1.포워드 프록시
![](/resource/img/forwardProxy.png)<br>
포워드 프락시(Forward Proxy)는 클라이언트가 타켓서버(목표서버)의 주소를 받아서 타켓서버로 연결을 시켜준다. 클라이언트는 타켓서버의 주소를 요청하면 프락시 서버는 뒷단에 타켓서버의 주소를 가진 서버에 연결을 포워딩 한다.<br>
 프락시 서버는 타켓서버의 주소를 가지고 있지 않다.


#### 2.리버스프록시
![](/resource/img/reverseProxy.png)<br>
리버스 프락시(Reverse Proxy)는 타켓서버의 주소가 아닌 프락시 서버가 타켓서버의 주소를 가지고 있고 프락시 서버가 이를 받아서 뒷단에 실제 타켓 서버로 연결을 시켜준다.<br> 그러니까 타켓서버의 주소를 프락시서버가 가지고 있어야 하며 클라이언트는 타켓서버의 주소로 요청을 하면 프락시 서버가 응답을 하게 된다.




## 게이트웨이 
![](/resource/img/gateWay.png)
게이트웨이의 동작은 프록시와 매우 유사하나 게이트웨이의 경우에는 그 다음에 있는 서버가 HTTP 서버 이외의 서비스를 제공하는 서버가 된다.<br>

클라이언트 <-(HTTP 통신) -> 게이트웨이 <-(HTTP 프로토콜 이외의 통신) -> HTTP이외의 서버

두 컴퓨터(노드-node라고도 함)가 네트워크 상에서 서로 연결되려면 동일한 통신 프로토콜(protocol, 통신 규약)을 사용해야 한다.<br>
따라서 프로토콜이 다른 네트워크 상의 컴퓨터와 통신하려면 두 프로토콜을 적절히 변환해 주는 변환기가 필요한데, 게이트웨이가 바로 이러한 변환기 역할을 한다.<br>
한국인과 미국인 사이에 원활한 의사소통을 위해 통역사를 두는 것과 동일하다 



## 캐시(Cache)
 캐시는 프록시 서버와 클라이언트의 로컬 디스크에 보관된 리소스의 사본을 가리킨다. <br>
 캐시를 사용하면 리소스를 가진 서버에 액세스를 줄이는 것이 가능하기 때문에 통신량과 통신 시간을 절약할 수 있다.<br>
 캐시 서버는 프록시 서버의 하나로 캐싱 프록시로 분류되며 캐시 서버의 장점은 같은 데이터를 몇 번이고 오리진 서버에 전송할 필요가 없다는 것이다.<br>
 (클라이언트는 네트워크에서 가까운 서버로부터 리소스를 얻을 수 있고 서버는 같은 리퀘스트를 매번 처리하지 않아도 된다)<br>



## 트래픽(Traffic)
데이터 전송량, 클라이언트의 입장에서 서비스 사용량<br>
웹 트래픽(Web traffic)은 웹 사이트에 방문하는 사람들이 데이터를 주고받은 양이다. 이는 인터넷 트래픽의 큰 부분이다. 이는 방문자 수와 방문 페이지 수에 따라 결정된다. <br>사이트들은 오고가는 트래픽을 감시하면서 사이트의 어느 부분이나 페이지가 유명한지, 또 특정 국가의 사람들이 어느 페이지를 가장 많이 보는지 등을 파악한다.<br>
 트래픽을 감시하는 방법은 다양하며 수집된 데이터는 사이트를 구성하고 보안 문제를 강조하며 잠재적인 대역 부족을 표시하는 데 참고할 수 있다. 




## DNS(Domain Name System Servers)
		-도메인 이름 시스템 서버
		-웹사이트를 위한 주소록
		-브라우저에 웹 주소를 입력할 때, 브라우저는 그 웹사이트를 검색하기 전에 DNS를 살펴봅니다.
		-브라우저는 HTTP메세지를 올바른 장소로 전송하기 위해 그 웹사이트가 있는 서버가 어떤것인지 찾아야한다.
		-브라우저는 DNS서버로 가서 입력된 URL에 맵핑되는 웹사이트의 경로를 찾는다.