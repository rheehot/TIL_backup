# JavaScript TIL 04

2021년 6월 17일에 작성된 문서입니다.
javascript 배운 내용을 정리했습니다.

## 반복문 (Iteration Statements)

반복문 : **같거나 비슷한 코드를 여러번 실행**시켜야 하는 경우 사용.

아래의 예시를 보자.
```javascript
let sum = 1; 
sum = sum + 2; //sum과 숫자의 합을 sum에 대입!
sum = sum + 3; 
sum = sum + 4;
// 조건 : 
//- 숫자(n)은 2부터 시작한다.
//- 숫자(n)은 4가 될 때까지 반복.
//- 숫자(n)는 1씩 증가.

console.log(sum);
```

<br>

### 반복문을 쓰는 순서

1. 본격적으로 반복문을 쓰려면, 아까 **반복할 내용을 먼저 코드로** 쓰자.
```javascript
let sum = 1; 
sum = sum + 2; //sum과 숫자의 합을 sum에 대입!
sum = sum + 3; 
sum = sum + 4; // ➡️ sum = sum + n 이 되겠지!

// 조건 : 
//- 숫자(n)은 2부터 시작한다.
//- 숫자(n)은 4가 될 때까지 반복.
//- 숫자(n)는 1씩 증가.

console.log(sum);
```
<br>

2. 반복할 **조건을 코드로** 써주자.
```javascript
let sum = 1; 
sum = sum + 2; //sum과 숫자의 합을 sum에 대입!
sum = sum + 3; 
sum = sum + 4; // ➡️ sum = sum + n 이 되겠지!

// 조건 : (조건을 코드로 써보자!)
let n = 2;//- 숫자(n)은 2부터 시작한다.
n <= 4;//- 숫자(n)은 4가 될 때까지 반복.
n = n + 1;//- 숫자(n)는 1씩 증가.
//이 나오게 된다.

console.log(sum);
```
<br>

---

### for 구문

1. 반복할 내용을 중괄호 block 안에 넣어준다.

	```javascript
	let sum = 1;
	for( ){
		sum = sum + n; // 반복할 내용!
	}
	console.log(sum);	
	```

2. 반복할 조건을 **초기화, 조건식, 증감문** 순으로 넣어준다.
	```javascript
	let sum = 1;
	for(let n = 2; n<=4; n = n + 1){
		sum = sum + n; // 반복할 내용!
	}
	console.log(sum); //10
	```
	초기화 : `let n = 2`
	조건식 : `n <= 4`
	증감문 : `n = n + 1`

<br><br>

---

### while 구문
* 반복할 조건 중, **초기화, 증감문은 따로, 조건식만 괄호에** 넣는다.

	```javascript
	let sum = 1; 
	let n = 2; // 초기화
	
	while(n<=4){ // 조건문이 괄호 안에
		sum = sum + n; // 반복할 내용!
		n = n + 1  // 증감문
	}
	console.log(sum); //10
	```	
	<br>


<br><br>
> Written with [StackEdit](https://stackedit.io/).
