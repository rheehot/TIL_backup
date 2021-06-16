# JavaScript TIL 03

2021년 6월 16일에 작성된 문서입니다.
javascript 배운 내용을 정리했습니다.

## 문자열 (String)
사실 문자열은 여기서 다 다루질 못한다. 왠만하면 구글링을 통해 검색을 해보거나 아니면 MDN문서를 보도록 하자!

### 문자열에 접근

#### `str [index]`
	
위의 `index`로 우리는 문자열에서 몇번째에 무슨 문자가 있는지 쉽게 알 수 있다.

```javascript
var str = 'CodeStates' //변수 선언
console.log(str[4]); //4번째의 문자는 'S'! 
					// 0번부터 카운팅을 시작한다.
```

하지만, 이 `index`로 접근은 가능한데 쓰지는 못한다. 
즉 `index`는 오직 **읽기 전용**인 셈이다.
```javascript
str[0] = 'G';
console.log(str); // 'CodeStates'지 'GodeStates'는 되질 못함.
```
<br>

### 문자열을 합치기

* `+` 연산자를 쓸 수 있다.
* `string` 타입과 다른 타입 사이에 `+`연산자를 쓰면, `string` 형식으로 변환이 된다.
* `str1.concat(str2, str3, ...);` 의 형태로도 사용 가능

```javascript
var str1 = 'Code';
var str2 = 'States';
console.log(str1 + str2); // 'CodeStates'
```
<br>

### 문자열의 전체 길이 반환
#### `str.length()`
```javascript
var str = 'CodeStates';
console.log(str.length); // 길이는 10
```
<br>

### 문자열에서 뭔가를 찾아보자
#### `str.indexOf(searchValue)`

* arguments : 찾고자 하는 문자열 (여기서 `searchValue`에 해당)
* return value : 처음으로 일치하는 index, 찾으려는 문자열이 없으면 -1 반환.
* `lastIndexOf`는 문자열의 뒤에서부터 찾는다.
* `str.includes(searchValue)` : 하나의 문자열이 다른 문자열에 **포함되어 있는지를 판별**하고, 결과를 `true` 또는 `false` 로 반환. (구형 브라우저에서 작동을 하지 않으므로 주의하자.)
```javascript
'Blue Whale'.indexOf('Blue'); //0 맨 첨부터 시작이니까
'canal'.lastIndexOf('a'); //3 뒤에서부터 세기 시작 
```
```javascript
var str = 'To be, or not to be, that is the question.';
console.log(str.includes('To be')); // true로 나온다.
```

<br>

### 문자열을 나누어 보자.
#### `str.split(seperator)`
* arguments : 분리 기준이 될 문자열 (여기서 `seperator`에 해당)
* return value : 분리된 문자열이 포함된 배열
* csv 형식(쉼표로 구분된 데이터 형식)을 처리할 때 유용.
```javascript
var str = 'Hello from the other side';
console.log(str.split(' ')); // 띄어쓰기 기준으로 나온다.
// ['Hello','from','the','other','side']
```

<br>

### 문자열 일부를 떼어 와보자.
#### `str.substring(start,end)`
* arguments : 시작 index, 끝 index (여기서 `start, end`에 해당)
* return value : 시작과 끝 index 사이의 문자열
*   index는 0부터 시작합니다
* `str.slice(start, end)`와 사용법이 비슷하다.
	* `substring()` : 매개변수로 입력받은 start index부터 length 길이만큼 string을 잘라내어 반환. 특정 문자열을 잘라내여 반환.
	* `slice( )` : 매개변수로 잘라내고 싶은 문자열의 start index와 last index를 전달

```javascript
var str = 'abcdefghij';
console.log(str.substring(0, 3)); // 'abc'
console.log(str.substring(1 4)); // 'bcd'
console.log(str.substring(-1, 4)); // 'abcd' 음수는 0 취급
```

<br>

### 문자열을 대문자나 소문자로 바꿔 보자.
#### `str.toLowerCase() / str.toUpperCase()` ➡️ `immutable`
* arguments : 없다.
* return value : 대, 소문자로 변환된 문자열
```javascript
console.log('ALPHABET'.toLowerCase()); // 'alphabet' 
console.log('alphabet'.toUpperCase()); // 'ALPHABET' 
```
<br>

#### `immutable`이란?
* **모든 string method는 immutable**하다.
* 즉, **원본이 안 변한다**는 것이다.
* array method는 때에 따라 다르므로, immutable 한지 mutable 한지 잘 기억해야한다.

<br>
<br>


> Written with [StackEdit](https://stackedit.io/).
