# Dispatcher Servlet
	- 이게 Spring에서 제공하는 프론트 컨트롤러
	- 이걸 생성하는게 처음이다. 
	- web. xml에서 생성합니다. 

## Spring 프론트 컨트롤러 패턴의 요청경로

![](/resource/img/spring/STS.jpg)

1. 요청 
2. dispatcher Servlet으로 이동 
	- 이동경로 설정은 "-servlet. xml"에서 bean을 생성하여 정한다. 
	- 요청의 해결방식을 자문하는 곳있다. (경로의 방향을 정해주는곳)
		=>HandlerMapping이라는 클래스에서 프론트에 들어와서 어떤 하위 컨트롤러로 이동할지 정한다. 

3.  하위 컨트롤러

4. 모델
	- request값을 전달받아서 처리를 한뒤 처리결과를 리턴한다. 

5. 하위 컨트롤러

6. dispatcher Servlet
	- 어떤 view로 보낼지 어떻게 정할까?
	- 하위 컨트롤러에서 이동할 view의 주소값을 내장해야한다. 
	- 이때 view의 방향을 결정할때 자문을 하는곳도 있다. 
		=>ViewResolver
		=>이 곳에 자문을 구해서 view의 경로를 정한다. 




**왜 Controller를 상속받은 컨트롤러를 프론트컨트롤러 역할로 사용하지 않는거지?
7. view로 이동. . .  


### 프론트 컨트롤러 패턴
	- 공통점이 있는  컨트롤러를 교통정리해주는 프론트 컨트롤러를 만든다. 