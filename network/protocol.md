# Protocol
- HTTP[hypertext transfer protocol] 
- FTP[file transfer protocol]
- ipx/spx



		
## P2P (Peer to Peer)
- 클라이언트가 될수도 있고 서버가 될수도 있다.
- 클라이언트와 서버의 구분은 역할이 기준이 된다.




## protocol
- 데이터전송에 필요한 협약.
- HTTP[hypertext transfer protocol] 
- FTP[file transfer protocol]
- ipx/spx

##  TCP/IP 
- (어떤 약속을했는지, 어떤특성을 가지고 있는지)
-  osi7계층. 서로다른 장치들이 어떻게 데이터를 주고 받을지에 대한 규제.
- 전송계층(실제 데이터를 보낼 수 있는 약속)
- TCP,UDP (컨셉, 이프로그램이 어떤 방식일지 정해야하는데 그 기준이 되는것이 TCP UDP)
- TCP(연결지향성)- 데이터 전송전에 선부터 깔아놓는다.(연결환경부터 셋팅함)
- 데이터를 안전하게 전송. (전화)
- 전송속도가 느릴 수 있다(UDP에 비교하여)
- 회선낭비할수 있다. (연결이 지속적으로 되어있으니까)
- 범용적 사용을 할 수 없다(연결을 탄력적으로 사용할 수 없기때문)(동시접속제한도..)
- 전문적 네트워크환경 설정에는 좋다.
- 응답신호를 받는다.


### UDP(비연결지향성)
- 데이터 보낼때만 순간적으로 연결한다.
- 연결을 지속적으로 유지하지 않는다.
- 안정적인 전송보장을 받을수 없다.
- 전송이 빠르다.
- 동시접속 허용(탄력적 접속이 가능하다)
- 멀티미디어 전송.




## Port

## Ip
- IP (식별하려고.)- 유일한 하나만을 구별하기 위함.
- 진짜IP 공식기관으로부터 부여받아 진짜로  딱 1개인 주소
- 유동아이피:할때마다 바껴		(아이피가부족하니까...) 계속쓴느게 아니니까 수거했다가 줬다가 함.
- 고정아이피:처음부터 끝까지 똑같음	(서버..)
- 가짜IP 내가 임의로 만든주소.(임의의 공간에서만 사용하는 가짜주소,정해진공간에서만 네트워크를 하는경우)

- 이런 유동아이피를 감시
- DHCP서버 : 아이피를 딱 가지고있어 내가 관리하는 컴터중에서 아이피를가지고있므면 수거한다.


## IP
- 컴퓨터를 찾아갈 수 있는 주소
- 아이피가 가진정보는 컴퓨터까지 밖에 없다.
- 네트워크는 각자의 문이 있다 그걸 포트라고 불린다.
- 그 문의 번호가 있어서 그걸 알아야 접근가능 
- 프로그램까지 통하는 번호
-  이 포트만 중복되지 않으면 된다. 포트가 똑같으면 다른 프로그램과 충돌우려

ex)  1~1024는 대부분 다른 포트로 예약이 되어있다.



## Socket
- 이 안에 ip랑 소켓을 포함한다.
