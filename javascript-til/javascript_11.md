# JavaScript TIL 11

2021년 7월 7일에 작성된 문서입니다.
javascript 배운 내용을 정리했습니다.
<br><br>
## 고차 함수란

#### 함수를 인자(argument)로 받을 수 있고, 함수의 형태로 리턴할 수 있는 함수

* **콜백 함수(callback function)** : **다른 함수(`caller`)의 인자(argument)로 전달되는 함수** 
* **커리 함수** : **'함수를 리턴하는 함수'**. 
	* 따로 커리 함수라는 용어를 사용하는 경우, 고차 함수를 '함수를 인자로 받는 함수'에만 한정. 
	* 고차 함수가 커리 함수를 포함. 

<br>

1.  **다른 함수를 인자로 받는 경우**
    
    ```jsx
    function double(num) {
      return num * 2;
    }
    
    function doubleNum(func, num) {
      return func(num);
    }
    
    /*
     * 함수 doubleNum은 다른 함수를 인자로 받는 고차 함수.
     * 함수 doubleNum의 첫 번째 인자 func에 함수가 들어올 경우
     * 함수 func는 함수 doubleNum의 콜백 함수.(인자)
     * 아래의 경우, 함수 double은 함수 doubleNum의 콜백 함수.(인자)
     */
     
    let output = doubleNum(double, 4);
    console.log(output); // -> 8
    ```
    <br>

    
2.  함수를 리턴하는 경우
    
    ```jsx
    function adder(added) {
      return function (num) {
        return num + added;
      };
    }
    
    /*
     * 함수 adder는 다른 함수를 리턴하는 고차 함수.
     * adder는 인자 한 개를 입력받아서 함수(익명 함수)를 리턴.
     * 리턴되는 익명 함수는 인자 한 개를 받아서 added와 더한 값을 리턴.
     */
    
    // adder(5)는 함수이므로 함수 호출 연산자 '()'를 사용 가능.
    let output = adder(5)(3); // -> 8
    console.log(output); // -> 8
    
    // adder가 리턴하는 함수를 변수에 저장할 수 있다.
    // javascript에서 함수는 일급 객체이기 때문.
    const add3 = adder(3);
    output = add3(2);
    console.log(output); // -> 5
    ```
    <br>

    
3.  **함수를 인자로 받고, 함수를 리턴**하는 경우
    
    ```jsx
    function double(num) {
      return num * 2;
    }
    
    function doubleAdder(added, func) {
      const doubled = func(added);
      return function (num) {
        return num + doubled;
      };
    }
    
    /*
     * 함수 doubleAdder는 고차 함수.
     * 함수 doubleAdder의 인자 func는 함수 doubleAdder의 콜백 함수.
     * 함수 double은 함수 doubleAdder의 콜백으로 전달.
     */
    
    // doubleAdder(5, double)는 함수이므로 
    // 함수 호출 기호 '()'를 사용할 수 있다.
    doubleAdder(5, double)(3); // -> 13
    
    // doubleAdder가 리턴하는 함수를 변수에 저장할 수 있다. (일급 객체)
    const addTwice3 = doubleAdder(3, double);
    addTwice3(2); // --> 8
    ```
<br><br>
## 고차함수 활용: map, filter, reduce

### map

>map 활용 시, 아래 과정을 꼭 기억하세요.
>
>-   **배열의 각 요소가**
>-   **특정 논리(함수)에 의해**
>-   **다른 요소로 지정(map) 됩니다.**

<br>


**map은 **하나의 데이터를 다른 데이터로** **맵핑(mapping)** 할 때 사용.**

```jsx
let arr = [1, 2, 3];

let result = arr.map(function(el){
	return el * 2; // 배열의 모든 요소를 2배로 만듦
});

result; // [2, 4, 6]
```
<br><br>

### filter 

>filter 활용 시, 아래 과정을 꼭 기억하세요.
>
>-   **배열의 각 요소가**
>-   **특정 논리(함수)에 따르면, 사실(boolean)일 때**
>-   **따로 분류합니다(filter).**

<br>


**filter는 조건에 맞는 데이터만 **분류(filtering)** 할 때 사용**.

```jsx
let arr = [1, 2, 3];

let result = arr.filter(function(el){
	return el % 2 !== 0; // 홀수인 배열의 요소만 분류
});

result; // [1, 3]
```
<br><br>
### reduce

>reduce 활용 시, 아래 과정을 꼭 기억하세요.
>
>-   **배열의 각 요소를**
>-   **특정 방법(함수)에 따라**
>-   원하는 **하나의 형태로**
>-   **응축합니다. (reduction)**

<br>

**reduce는 여러 데이터를, 하나의 데이터로 **응축(reduce)**할 때 사용**

```jsx
let arr = [1, 2, 3];

let result = arr.reduce(function(acc, cur){
	acc + cur; //배열의 모든 요소의 합을 누적 계산
	return acc //누적한 값을 리턴
},0);
// 0은 초기값. 만약 안쓰면 배열의 맨 첫번째 요소가 초기값이 된다.

result; // 6
```

<br>
<br>

---

### reduce의 색다른 사용법

### 1. 배열을 문자열로

#### 수도코드

>-   배열의 각 요소 : 유저 정보
>-   응축하는 방법 (함수) : 하나의 유저의 이름과 쉼표를 이어 붙임(concat)
>-   원하는 형태 : 문자열로 누적.
>-   응축된 결과 : 쉼표로 구분되는 모든 유저의 이름

```jsx
function joinName(resultStr, user) {
  resultStr = resultStr + user.name + ', ';
  return resultStr;
}

let users = [
  { name: 'Tim', age: 40 },
  { name: 'Satya', age: 30 },
  { name: 'Sundar', age: 50 }
];

users.reduce(joinName, '');
// 콜백 함수 joinName은 users 배열 안에 있는 요소의 이름을 하나로 응축
```



<br>


### 2. 배열을 객체로

#### 수도코드

>-   배열의 각 요소 : 유저 정보
>-   응축하는 방법 (함수) : 유저 한 명의 이름 중 첫 글자를 주소록 객체 속성의 키(key)로, 유저의 정보를 주소록 객체 속성의 값(value)으로 추가.
>-   원하는 형태 : 주소록 객체에 누적.
>-   응축된 결과 : 모든 유저의 정보가 알파벳으로 구분된 주소록

```jsx
function makeAddressBook(addressBook, user) {
  let firstLetter = user.name[0];

  if(firstLetter in addressBook) {
    addressBook[firstLetter].push(user);
  } else {
    addressBook[firstLetter] = [];
    addressBook[firstLetter].push(user);
  }

  return addressBook;
}

let users = [
  { name: 'Tim', age: 40 },
  { name: 'Satya', age: 30 },
  { name: 'Sundar', age: 50 }
];

users.reduce(makeAddressBook, {});
// 콜백 함수 makeAddressBook은 
// users 배열 안에 있는 요소로 주소록을 만든다.
```

  


<br><br><br>

> Written with [StackEdit](https://stackedit.io/).
