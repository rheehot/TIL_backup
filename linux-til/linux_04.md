# Linux TIL 04

2021년 6월 23일에 작성된 문서 4번 입니다.
linux 배운 내용을 정리했습니다.

## npm & package.json

* **런타임**: **프로그래밍 언어가 실행되는 환경**
 * **node.js**: **JavaScript 런타임**


```
// runnode.js
const testFunction = function(arg){
    console.log("Arg is : ", arg);
}

testFunction(20);

//runnode.js 파일에 
//testFunction이라는 함수를 작성
```


```
node runnode.js
// 명령어 `node`로 실행
```



### nvm 이란

**nvm**: **다양한 node version를 설치하고 관리할 수 있는 프로그램** 
```
nvm ls // 설치한 node version들
```
```
nvm install 12.18.3 // 특정 버전 node 설치
```
---

### npm과 package.json

>하나의 프로그램은 **다양한 모듈**이 합쳐져서 만들어집니다. 
우리는 우리보다 잘하는 사람들이 만들어놓은 **검증된 코드(모듈)를 가져다가 사용**합니다.

#### npm
* **node.js**에서 외부 라이브러리를 다운로드 방법 : **npm** (대표적) 
	* **npm**은 **Node Package Manager**로 일종의 앱스토어. 
	* **필요한 모듈을 다운로드할 수 있는 모듈들이 모여있는** 곳 
	* **node.js 생태계의 패키지 매니저** 

#### package.json
* 프로그램을 실행시키기 위해 필요한 모듈, 프로그램을 실행시키는 방법, 프로그램을 테스트하는 방법 등이 명시 
* 프로그램을 실행시키기 위해 필요한 **실제 모듈은 따로 node_modules이라는 폴더에 저장**된다. 
* **package.json**에는 **어떤 모듈이 들어가 있는지**를 알 수 있다. (프로그램의 카탈로그) 

---
### package.json의 이점

* 프로젝트 코드를 전달시, 포함하는 **모든 모듈을 다 전달하지 않아도** 된다. 
* package.json에서 **필요하다고 하는 모듈을 npm을 이용해 다운**. 
	* npm install 명령어로 package.json에서 필요로 하는 모듈을 다운. 
	* npm install이 완료되면 node_modules 디렉토리가 생성

---
### package.json 살펴보기

**devDependencies** 
* **키**에 적힌 것은 **모듈 이름**. **값**은 **버전**. (JSON 형식)
* 프로그램 실행과 관계 없는 오직 **개발 환경에서 필요한 모듈**이 적혀 있다. 
	* 의존성 모듈
	* 코드 모양을 잡아주는 lint나 테스팅 모듈 (예시임)
	* **실제 프로젝트 동작에 직접적으로 영향을 주지 않는 모듈들 명시**

* `$ npm install` : npm에 있는 모듈을 설치 
* `--save-dev` 옵션과 함께 설치: 자동으로 devDependencies에 추가

<br>

**dependencies** 

* 프로그램 **직접 실행에 반드시 필요한 모듈들**이 적혀 있다. 
	* underscore 또는 React (예시임)
* `--save` 옵션과 함께 설치: 자동으로 dependencies에 추가됩니다. 

<br>

**scripts**
* CLI에서 사용가능한 명령을 기술 (npm script)
* CLI에서 실행할 때 : `npm run <스크립트 이름>` 으로 실행
* 이어지는 화면에 해당 npm script가 어떤 내용을 실행하는지 확인 가능
* 주로 실행, 테스트, 코드 검사(lint) 등을 기술. 
	* 항상 모든 프로젝트에 있는 것은 아님
	* 테스트 케이스 통과만 목적이면, start 스크립트 조차 없을 수 있다.
* 주로 기술하는 항목들
	|작업 내용|실행 스크립트|
	|:---|:---|
	|node.js 실행|`npm run start`|
	|테스트 실행|`npm run test`|
	|코드 검사|`npm run lint`|
	|과제 제출(공부할 때만)|`npm run submit`|



<br><br><br>

> Written with [StackEdit](https://stackedit.io/).
