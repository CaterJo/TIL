


3.연산자(Operator)
(1)산술 연산자(Arithmetic Operator)
	{ *,/,%,+,-,++,-- }
++,-- : 증감연산자,단항연산자.

=>결과값이 숫자.

(2)비교연산자(compare Operate)
	>,<,>=,<=,==,!=

=>결과값이 참,거짓, true,false





(3)논리연산자(logical operate)
&&(and연산자),||(or),!(not연산자)

and는 둘다 참이어야참
or는 둘중 하나만 참이어도참.


진리표

a	b	a&&b	a||b	!a
T	T	 T       T	F
T	F	 F	 T	F
F	T	 F	 T	T
F	F	 F	 F	T




!(not) 토글스위치




(4)대입연산자.

=,+=,-=,/=


대입산자와 복합대인연사ㅣㄴ자에는 어떤차이가 있을까?





**연산자에서 가장 주의해야할점은 바로 연산순서이다.
-연산순서에 의해서 결과값이 달라진다는점을 주의해야한다.
-순서를 외워서 프로그램을 짠다? 존나 무의미하다.
-괄호를 묶어주는게 안전하다. 연산순서를 외우려고하다보면 언젠가 실수가 발생한다.







(5)비트 연산자.
->이진수 연산을한다 ㅠㅠ
->성능상으로는 쉽게 전달이된다.
->그냥 이런게 있구나 정도로만 알고만있자.


&,|,^,<<,>>,>>>,~

	& (and)
	| (or)
	^ (xor) : 익스클로시브 or
	>>,>>>,<< : shift연산자
	~ : (comlpement) 보수. complement

->진법을 변환해야지 사용할수있다.






//데이터준비가 항상시작이다!!



대입연산자가 사용되면 우항의 연산이 먼저 연산을한다.
좌항에는 공간, 우항에는 데이터가 온다.
우항의 데이터를 좌항의 공간에 대입한다.


코드는 무조건 단순하게 만드는게 최고다!!








## ^(xor)
데이터를 암호화하는 방법임.
진리표를 통해서 이 비트연산자의 기능을 알아보겠음 ㅎㅎ

a	b	a^b
T	T	F
T	F	T
F	T	T
T	F	F


헐 이거 논리가 뭐지?


같은 신호가 들어오면 거짓
서로 다른신호가 들어오면 참.

이게 왜 암호화를 하는데 도움을 줌????


내가 누군가에게 데이터를 보낸다고 하자.
그 데이터가 11010010이라는 데이터를 보낸다.
이걸 그대로 보내면 외부노출될 가능성이있다.
이걸 암호화하기 위한 키값이 만들고 그걸 공유하면된다.

11010010
//임의의 키값 10101100

11010010
10101100
--------
0111110 이렇게 xOR연산을 통해서 데이터를 암호화한다.
이렇게 암호화된 코드를 전송한뒤 키값을 공유하면 데이터를 쉽게 암호화할수있다.








(6)캐스팅 연산자. : 강제 형변환 연산자.
//이게 뭐지?
//강제 형변환 연산자.

(데이터타입) 변수 


캐스팅에는 두가지가 있다고 할수있다.
-명시적방법
-묵시적인방법

명시적이란것은 앞에 데이터형을 알려줘서 써준다는거고
묵시적이란것은 써주지 않아도 자연스럽게 생략된 개념임...
(작은 타입에서 큰 타입으로 형변환이 이루어질때는 묵시적 형변환이 허용된다.)




###부동소수점
-소수점이 움직인다.
-한마디로 실수라는 말이다...


###기계자체는 정수형으로 처리된다.
그렇지만 실수는 바로 직접적인 처리가 되지 않고 별도의 메모리장소에 지수부와 가수부로 나뉘어서 저장된다.
왜 별도로 저장하냐? 컴퓨터상에는 실수라는 개념이 없고 오로지 정수로 처리되며
실수를 표현히기 위해서 지수파트와 가수파트를 나누어서 메모리에 저장했다가
출력을 해야할때 이를 결합하여 출력하게된다.
따라서 정수를 변수에 대입할때와는 다르게 메모리를 거쳐서 대입이 되는데
이때 실수의 디폴트값이 (double)이다. 그렇기때문에 float 형태였다면 형변환이 필요하게된다.





##간단한 프로그램이라도 직접만들어본다 그게 중요함!
#이론적인 개념은 이미지화해서 받아드리면 편하게 이해할수있다.





(7)삼항연산자.
=>연산자가 3개다.
=>일종의 조건문으로써 true일경우 실행문과 false일경우의 실행문을 각각적어준다.

<문법> 조건식?참:거짓



