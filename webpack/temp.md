

# 모듈
표준이 있음.
1. CommonJS(Node.js)
2. ESM(ECMAScript)


모듈의 강점
- 코드 재사용성증가
- 코드 관리가 편해짐
- 코드를 모듈화하는 기준이 명학해야한다.


# 번들 (bundle)

웹팩을 사용하면 웹에 사용되는 다양한 파일들을 모듈로 다룰 수 있다.
참조관계에 있는 파일들을 하나로 묶는것을 번들링이라고 한다. 

## 번들이 중요한 이유
1. 모든 모듈을 로드하기 위해 검색하는 시간이 단축된다.
	- 하나의 파일에 모두 담기기 때문.
2. 사용하지 않는 코드를 제거해준다.
	 - 파일 크기가 감소한다. 
3. 파일의 크기를 줄여준다.
	- 별도의 파일을 압축하는 것보다 번들링된 파일을 압축하는것이 더 많이 줄여준다.



## 웹팩의 구성요소 

### Entry
모듈의 의존 관계를 이해하기 위한 시작점을 설정.	


### output
webpqck이 생성하는 번들 파일에 대한 정보를 설정



## package.json
프로젝트 관리를 하는 파일
- 어플리케이션 내부에 직접 포함되는 모듈
- 개발과정에 필요한 모듈(devDependencies)
	- 파일 문법검사해주는 모듈
	- --save-dev


## loader
다양한 모듈들을 입력받아 처리하는 역할
- css를 js파일로 만든다.

	


코드의 실행환경이 node라는것을 알려줘야 node의 내장 모듈을 인식한다
npx webpack --target=node


## Css loader
- css를 모듈로 다루기 위해 사용하는 로더
