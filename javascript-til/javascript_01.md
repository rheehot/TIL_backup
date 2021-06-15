
# JavaScript TIL 01

2021년 6월 15일에 작성된 문서 1번 입니다.
(문서 2번은 다음 포스팅에 정리해두었습니다.)
javascript 배운 내용을 정리했습니다.

<br>

## 변수 (Variable)

**변수: 데이터를 다루는 방법**

아래의 구구단을 만드는 식을 전부 쳐보자.
```javascript
console.log(3 * 1)
console.log(3 * 2)
console.log(3 * 3)
console.log(3 * 4)
console.log(3 * 5)
console.log(3 * 6)
console.log(3 * 7)
console.log(3 * 8)
console.log(3 * 9)
```
이거를 치면 손이 아프다. 이 때, 우리는 3을 변수로 선언 할 수 있다. 아래처럼. 그럼 일일이 3을 쳐야하는 수고를 덜 수 있다.
```javascript 
let num = 3;
```

---
<br>

* **변수란 무엇일까?**

	변수는 우리가 동일한 사이즈의 **데이터 보관함(메모리)에 붙이는 이름** 이라고 생각하면 쉽다. 그리고 이 변수는 **재사용이 가능**하다.

* **변수를 사용하는 방법**
  
  1. **선언(declaration)**: 보관함을 확보하는 단계
		
		`let age;` 
		
		`let`: 변수 선언 부분, `age`: 변수의 이름
  2. **할당(assignment)**: 보관함에 데이터를 저장한다.
	  	
	  	`age = 12;`

		아까는 `age`를 선언만 했지, 할당은 하지 않았다.
		이제는 `age`에 `12`가 할당되었다.  
	
	3. **선언과 할당은 동시에 가능**하다.	
	
		`let age = 12;`
	
	위의 1번과 2번은 선언따로, 할당따로했지만 동시에도 가능하다.

<br>
<br>

## 타입 (Variable)

아까 위에서 배운 내용을 다시 한 번 짚고 가자.

변수는 **상황에 따라 변할 수 있는 값**이다.

즉, `myname`이라는 변수에는 **들어갈 수 있는 값이 다르다**는 것이다.

* 선언은 `let myname;`
	* **선언은 `let`으로 1번만** 할 수 있다.
* 할당은 `myname = 'Steve';`
	* 여기서 `=` 은 **같다가 아니라, 대입**한다의 뜻!
* 이 둘을 같이 쓰면, `let myname = 'Steve';`

<br>


프로그래밍에서 **변수는 이름(Label)이 붙은 값**이다.
위의 `myname`이라는 변수를 써서 다른곳에도 `'Steve'`를 쓸 수 있다. 대표적인 예시로는 원주율이나 빛의 속도가 있다.

``` javascript
let pi = 3.141592;
let speedOfLight = 300000000;
```
위의 변수를 이용한 표현식을 보자.
```javascript
pi * 5 * 5 // 반지름이 5인 원의 넓이
```
물론 여기서도 5를 따로 변수 `radius`로 선언 가능하다.
그리고 **결과물은 다시 변수로 담을 수도** 있다.
```javascript
let areaOfCircle = pi * radius * radius;
```
이 때, 변수명은 공백을 못써서 보통 단어 첫 글자를 대문자로 써 붙인다. (Camel Case)

<br>

또 변수는 **같은 변수를 이용해서 대입할 수 있다**. 아래의 예시를 보자.
```javascript
let sum = 1;
sum = sum + 2;// sum에 이미 할당된 sum + 2를 대입 
sum = sum + 3; // 한 번 선언한 변수를 다시 쓸 떄에는 let을 쓰지 않는다.
```

그렇다면, 할당이 없는 변수는 어떻게 될까?
바로, `undefined` ! ➡️ **정의 되지 않다**

----
<br>

* 변수의 타입 (다양한 타입이 존재)

| 변수 이름 | 변수 타입 | 예시 |
| :----: | :----: | :--------: |
| pi | 숫자 | 3.141592 |
| myname | 문자열 | Steve |
| isAdult | 불리언(Boolean) **true / false** | 성인입니까? |
<br>


* compound 타입 (자료형이 섞인)

| 변수 타입 | 자료들(?) | 예시 |
| :-------: | :-------: | :--------: |
| 배열 | banana, pineapple, kiwi | `let fruits = [ 'banana','pineapple', 'kiwi'];` |
|객체|이름, 나이, 체크표기| `let person = { name: 'Steve', age: 32, isStudent: true};`|


* 위에서 잠깐 본, **undefined도 타입**이다.
* **함수 역시 타입**이다.
<br><br><br>
<br>


## 함수 (Function)
```javascript
function mulTablePrinter(num){
console.log(num * 1);
console.log(num * 2);
console.log(num * 3);
```
여기서 `function mulTablePrinter(num){`을 보면,
함수는 각각 `keyword//여기선 function`, `name//여기선 mulTablePrinter`, `parameter//여기선 num`,`body//아래 콘솔들`로 이루어진 걸 알 수 있다.

이런 함수는,

* **코드의 묶음**들 (일종의 즐겨찾기 버튼)
* **기능**(function)의 단위
* 입력과 출력간의 **매핑**(mapping)
* 반드시 돌아오는 **return**

의 의미를 지닌다고 할 수 있다.  

즉, **어떤 목적을 가진 작업들을 수행하는 코드들이 모인 블록**이다! 그리고 함수는 **항상 출력값을 반환**한다!

---
<br>

* 함수를 사용하는 방법

	1. 선언(declaration): 
		```javascript
		function cal(param1, param2){
		console.log(param1 + param2);
		return param1 * 10;
		}
		```
	2. 호출(call, invocation):
		```javascript
		cal(10,20);	
		```
	이 2번의 `cal(10, 20);` 속 10과 20이 `cal` 함수 속의 `param1`, `param2`에 들어가서 함수가 실행된다.

----
<br>

* 함수 선언 방법 3가지!
  
 1. 함수 선언식

```javascript
function getTriangleArea(base, height){
	let triangleArea = (base * height) / 2;
	return triangleArea
};
```
<br>
   
2. 함수 표현식
```javascript
const getTriangleArea = function (base, height){
	let triangleArea = (base * height) / 2;
	return triangleArea
}; //익명의 함수를 할당한 것이다.
```
여기서 `const getTriangleArea` 부분은 변수를 선언해 준 것이다.

<br>

3. 화살표 함수
```javascript
const getTriangleArea = (base, height) => {
	let triangleArea = base * height ;
	return triangleArea
};
```
* 화살표 함수의 경우, 함수 **본문(body)에 return문만** 있는 경우, **return과 {} 중괄호를 생략할 수 있다.**

```javascript
const getTriangleArea = (base,height) => base * height / 2; // O 정상적으로 작동한다.
const getTriangleArea = (base,height) => {base * height / 2}; // X undefined를 리턴한다.
```

* **return 문에서 소괄호를 사용할 수** 있다.
```javascript
const getTriangleArea = (base,height) => (base * height / 2); O 정상적으로 작동한다.
```

* 만약 함수 내의 표현식이 2줄을 넘어갈 경우에는 return과 중괄호를 명시적으로 쓰도록 하자.
---

<br>


* 함수의 호출
1. 선언
```javascript
function getTriangleArea(base, height){
	let triangleArea = (base * height) / 2;
};
```
여기서 `base`와 `height`는 **매개변수(parameter)**다.
<br>
<br>

2.  호출
```javascript
getTriangleArea(3, 4);
```
여기서는 `3`과 `4`가 **전달 인자(argument)** 가 된다.

<br>
<br>
<br>


> Written with [StackEdit](https://stackedit.io/).
