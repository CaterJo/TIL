

###  인터페이스(Interface)
1) 클래스를 만들기 위한 설계도
	- 클래스의 부모격이다.
2) 표준화를 위한 약속, 규칙.
3) 객체간의 의존성을 최소화시킨다.	
4) 완전(순수) 추상클래스. //문법적으로 완전한 추상클래스
추상클래스의 역할을 좀더 전문적으로 처리하기위함.
5) implements 키워드사용.
6) 인터페이스들끼리 상속이가능하다.	이때는 extends
7) 인터페이스는 100% 추상메서드만 있다.
 - 그냥 껍대기 가이드만 제공한다.
 - 절대 일반메서드를 만들수 없다.
 - 클래스를 잘 만들기 위한 가이드
 - 클래스 설계에 대한 가이드.

 - 비교) 너 주식 어디사면 잘될꺼야(실질적인 조언=>클래스)
 	 야 너 잘살아야돼 (추상적인 조언=>인터페이스)


- 인터페이스 안의 변수는 기본적으로 static이다.
- 인터페이스값에 있는 변수는 final 변수 즉 상수다.
- 인터페이스 변수는 public도 숨겨져있다. 많이 쓸수록좋다.
- public static final
- 무조건 오버라이딩해야한다.
- 쓸데없는것을 오버라이딩해야하는 문제가 생김..(단일상속일경우)
- 그래서 기능별로 인터페이스를 나눠놔서 필요한걸 골라받을수 있게 해야한다.
- 이때 다중상속으로 인한 기능적 트러블이 생기지 않는 이유는 기능이 없는 추상클래스이기 때문이다.
- 인터페이스를 상속받을때 쓰는 키워드
- implements 인스턴스명
- 추상메서드에서 public을 붙여야한다.

