# JavaScript TIL 06

2021년 6월 28일에 작성된 문서입니다.
javascript 배운 내용을 정리했습니다.


<br>

## 객체

### 객체의 선언
```javascript
let user = {
	firstName : 'John'
	lastName : 'Lee'
	email : 'aaaa@codestates.com';
	city : 'Seoul';
}
```
* 객체는 **키와 값의 쌍**으로 이루어져 있다.
	* 키 : `firstName`, `lastName`, `email`, `city`
	* 값 : `'John'`, `'Lee'`, `'aaaa@codestates.com'`, `'Seoul'`
* 키랑 값은 **`:` 로 구분** 짓는다.
* **중괄호`{}`를 이용해서 객체를 만든다**.
* 키-값의 **쌍은 `,`로 구분** 짓는다.

<br>

### 객체 값 사용 방법 2가지
1. Dot notation
```javascript
let user = {
	firstName : 'John'
	lastName : 'Lee'
	email : 'aaaa@codestates.com';
	city : 'Seoul';
}

user.firstName; // 'John'
user.city; // 'Seoul'
```
2. Bracket notation
```javascript
let user = {
	firstName : 'John'
	lastName : 'Lee'
	email : 'aaaa@codestates.com';
	city : 'Seoul';
}

user['firstName']; // 'John'
user['city']; // 'Seoul'
```
<br>

하지만 여기서 **`user[city]`라고 쓴다면 에러가 발생**한다.
이 에러는 **`city`라는** **정의 되지 않은 변수를 참조하기에 발생**한다.

따라서 `[]`안에 문자열이 아니라 **변수를 쓰고 싶을 때는 객체 안의 키가 유동적일 경우에 쓰는 것**이 좋다.
<br>
<br>

### 객체로 더  할 수 있는 것들

#### 1. `delete` 를 이용해 삭제하기

```javascript
let user = {
	firstName : 'John'
	lastName : 'Lee'
	email : 'aaaa@codestates.com';
	city : 'Seoul';
}

delete user.city; // city 키-값 쌍을 지운다.
```
`delete user.city;`로 `city` 키-값 쌍을 지우면 객체는 아래와 같이 변한다.
```javascript
let user = {
	firstName : 'John'
	lastName : 'Lee'
	email : 'aaaa@codestates.com';
}
```
`city` 키-값 쌍이 지워진 것을 알 수 있다.

<br>

#### 2. `Dot notation`,`Bracket notation` 를 이용해 값 추가

```javascript
let user = {
	firstName : 'John'
	lastName : 'Lee'
	email : 'aaaa@codestates.com';
	city : 'Seoul';
}

user.category = 'hello'; // Dot notation 써서 값 추가
user['otherThing'] = 'hi'; // Bracket notation 써서 값 추가
```
`Dot notation`,`Bracket notation` 를 이용해 값 추가하면 아래와 같아진다.
```javascript
let user = {
	firstName : 'John'
	lastName : 'Lee'
	email : 'aaaa@codestates.com';
	city : 'Seoul';
	category = 'hello';
	otherThing = 'hi';
}
```
`city` 키 아래에 값들이 추가 된 것을 알 수 있다.

<br>

#### 3. `in` 연산자 를 이용해 해당하는 키가 있는지 살피기

```javascript
let user = {
	firstName : 'John'
	lastName : 'Lee'
	email : 'aaaa@codestates.com';
	city : 'Seoul';
}

'lastName' in user; // true
'content' in user; // false
```
만약 해당하는 키가 있다면 `true`를, 해당하는 키가 없다면 `false`를 반환한다.


<br><br><br>

> Written with [StackEdit](https://stackedit.io/).
