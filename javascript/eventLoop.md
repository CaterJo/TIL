# Event Loop

## 한줄 요약
자바스크립트의 동시성(Concurrency)을 지원하는 것이 바로 이벤트 루프(Event Loop)이다.


## intro
자바스크립트의 큰 특징 중 하나는 '단일 스레드'기반 언어라는 점입니다. 스레드가 하나라는 말은 곧 동시에 하나의 작업만을 처리할 수 있다는 말입니다. 하지만 실제 브라우저나 Node.js같은 자바스크립트 실행환경에서는 동시에 많은 작업을 처리합니다.  
Node.js기반의 웹서버에서는 동시에 여러개의 HTTP요청을 처리하기도 하죠. 어떻게 싱글 스레드인 자바스크립트가 이런 동시성(Concurrency)를 지원할 수 있는걸까요?

정답은 바로 `Event Loop`입니다. 자바스크립트는 `Event Loop`를 이용해서 비동기 방식으로 동시성을 지원합니다. 하지만 ECMAScript의 스펙에는 `Event Loop`가 없습니다. 좀 더 정확히는 비동기나 동시성에 대한 언급이 없습니다. 자바스크립트 인진은 단지 단일 호출스택(Call stack)을 사용하여 요청이 들어올 떄마다 해당 요청을 순차적으로 호출스택에 담아 처리할 뿐이죠. 그럼 비동기 요청은 어떻게 이루어지며, 동시성에 대한 처리는 누가 하는걸까요? 바로 자바스크립트 엔진의 구동환경인 브라우저나 Node.js에서 지원합니다.  


![](/resource/img/javascript/browerEnv.png)  
위 그림을 보면 비동기요청을하는 `XMLHttpRequest`나 `setTimeout`같은 함수들이 자바스크립트 엔진과는 별도로 Web API의 영역에 따로 분류되어 있습니다. `Event Loop`나 `Task Queue`같은 장치도 외부에 구성되어 있는걸 볼 수 있습니다.  
이처럼 자바스크립트 엔진에서 직접 처리하는 것이 아니라  API를 통해 브라우저에 위임을 합니다.  위임했던 일이 끝나면 Task Queue에 추가가 됩니다. `Event Loop`는 호출 스택이 비워질 때마다 `Task Queue`에서 가장 오래된 작업을 꺼내와서 해당 작업에 대한 콜백을 실행시킵니다. 
이번엔 Node.js의 실행환경을 한번 보겠습니다.

![](/resource/img/javascript/nodeEnv.jpg)  
위 구성을 보면 Node.js는 비동기 IO를 지원하기 위해 libuv라이브러리를 사용하며, 이 라이브러리에서 이벤트 루프를 제공합니다. 자바스크립트 엔진은 비동기 작업을 위해 Node.js의 비동기 API를 호출하면 libuv의 `Evnet loop`가 콜백의 스케쥴을 관리하고 실행합니다.  

자바스크립트는 단일스레드 기반의 언어입니다. 이 말을 자세히 풀어보면 '자바스크립트 엔진이 단일 호출 스택을 사용한다'는 관점에서 보면 맞는 말입니다. 하지만 실제로 자바스크립트가 구동되는 브라우져나 Node.js같은 환경에서는 멀티스레드가 사용되며 이런 구동환경이 단일 호출 스택을 사용하는 자바스크립트 엔진과 상호 연동하기 위해 사용하는 장치가 바로 이벤트 루프인 것입니다.



## REF
- [이벤트 루프 시각화]( http://latentflip.com/loupe/ )
- [이벤트 루프](https://meetup.toast.com/posts/89)
- [자바스크립트의 비동기 처리](https://helloworldjavascript.net/pages/285-async.html)
- [자바스크립트의 비동기 처리2](http://sculove.github.io/blog/2018/01/18/javascriptflow/)
