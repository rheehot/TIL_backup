# JavaScript TIL 09

2021년 7월 2일에 작성된 문서입니다.
javascript 배운 내용을 정리했습니다.

<br>

## Spread/Rest 문법


### Spread 문법

**배열을 풀어서 인자로 전달**하거나, **배열을 풀어서 각각의 요소로 넣을 때** 사용.

```javascript
function sum(x, y, z) {
  return x + y + z;
}

const numbers = [1, 2, 3];

sum(...numbers) // 질문: 어떤 값을 리턴하나요?
```
* `sum(...numbers)`는 6을 리턴. **(각각의 인자로 전달됨.)**

<br><br>

### Rest 문법

**파라미터를 배열의 형태로 받아서 사용**가능. 
**파라미터 개수가 가변적일 때 유용**.

```javascript
function sum(...theArgs) {
  return theArgs.reduce((previous, current) => {
    return previous + current;
  });
}

sum(1,2,3) // 질문: 어떤 값을 리턴하나요?
sum(1,2,3,4) // 질문: 어떤 값을 리턴하나요?
```
* `sum(1,2,3)`은 6을 리턴 **(배열의 형태로 받아서 사용)**
* `sum(1,2,3,4)`은 10을 리턴

<br><br>

## 배열에서 사용하기

**Spread** 문법은 **배열에서 강력한 힘을 발휘**합니다.

### 1. 배열 합치기

```javascript
let parts = ['shoulders', 'knees'];
let lyrics = ['head', ...parts, 'and', 'toes'];

// 질문: lyrics의 값은 무엇인가요?
```
* `lyrics` = `["head", "shoulders", "knees", "and", "toes"]`가 나온다. **(배열이 합쳐짐)**

<br>

```javascript
let arr1 = [0, 1, 2];
let arr2 = [3, 4, 5];
arr1 = [...arr1, ...arr2];  

// 참고: spread 문법은 기존 배열을 변경하지 않으므로(immutable), 
// arr1의 값을 바꾸려면 새롭게 할당해야 합니다.

// 질문: arr1의 값은 무엇인가요?
```
* `arr1` = `[0, 1, 2, 3, 4, 5]` 가 나온다. **(배열이 합쳐짐)**

<br>

### 2. 배열 복사

```javascript
let arr = [1, 2, 3];
let arr2 = [...arr]; // arr.slice() 와 유사
arr2.push(4);  

// 참고: spread 문법은 기존 배열을 변경하지 않으므로 (immutable)
// arr2를 수정한다고, arr이 바뀌지 않습니다.

// 질문: arr와 arr2의 값은 각각 무엇인가요?
```
* `arr1` = `[1, 2, 3]`
* `arr2` = `[1, 2, 3, 4]` **(`arr1`의 요소가 복사됨.)**
<br><br>

## 객체에서 사용하기

```javascript
let obj1 = { foo: 'bar', x: 42 };
let obj2 = { foo: 'baz', y: 13 };

let clonedObj = { ...obj1 };
let mergedObj = { ...obj1, ...obj2 };

// 질문: clonedObj와 mergedObj의 값은 각각 무엇인가요?
```
* `coneObj` = `{foo: "bar", x: 42}` **(객체에서도 쓰임)**
* `mergedObj` = `{foo: "baz", x: 42, y: 13}`
<br><br>

## 함수에서 나머지 파라미터 받아오기

```javascript
function myFun(a, b, ...manyMoreArgs) {
  console.log("a", a);
  console.log("b", b);
  console.log("manyMoreArgs", manyMoreArgs);
}

myFun("one", "two", "three", "four", "five", "six");

// 질문: 콘솔은 순서대로 어떻게 찍힐까요?
```
아래와 같이 나온다.
``` javascript
a one
b two
manyMoreArgs (4) ["three", "four", "five", "six"]
```
**함수에서 남은 파라미터들을 객체에서 가져왔다.**

<br><br>

## 구조 분해 (Destructing)

**Spread 문법으로 값을 해체한 후, 개별 값을 변수에 새로 할당하는 과정**

## 분해 후 새 변수에 할당

### 배열

```javascript
const [a, b, ...rest] = [10, 20, 30, 40, 50];

// 질문: a, b, rest는 각각 어떤 값인가요?
```
* `a` = 10
* `b` = 20
* `rest` = `[30, 40, 50]` **(분해한 뒤, `rest`에 할당)**

<br>

### 객체

```javascript
const {a, b, ...rest} = {a: 10, b: 20, c: 30, d: 40}
// 질문: a, b, rest는 각각 어떤 값인가요?
```
* `a` = 10
* `b` = 20
* `rest` = `{c: 30, d: 40}` **(분해한 뒤, `rest`에 할당)**
<br>

-   **객체**에서 **구조 분해 할당을 사용하는 경우, 선언(`const`, `let`, `var`)과 함께 사용하지 않으면 에러가 발생**할 수 있다.


<br><br>

## 유용한 예제: 함수에서 객체 분해

```javascript
function whois({displayName: displayName, fullName: {firstName: name}}){
  console.log(displayName + " is " + name);
}

let user = {
  id: 42,
  displayName: "jdoe",
  fullName: {
      firstName: "John",
      lastName: "Doe"
  }
};

whois(user) // 질문: 콘솔에서 어떻게 출력될까요?
```
* `jdoe is John`이 출력된다.

<br><br><br>

> Written with [StackEdit](https://stackedit.io/).
