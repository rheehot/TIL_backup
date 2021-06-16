

# JavaScript TIL 02

2021년 6월 15일에 작성된 문서 2번 입니다.
javascript 배운 내용을 정리했습니다.

## 조건문 (Conditional Statement)

조건문은 어떤 **조건을 판별하는 기준**을 만드는 것!
반드시 **비교 연산자(comparsion operator)**가 필요.

* 다양한 비교 연산자들

|기호| 뜻 |
|:---:|:---:|
|>|초과|
|<|미만|
|>=|이상|
|<=|이하|
|===|같다|
|!==|다르다|

**비교의 결과**는 늘 Boolean, 즉 **true or false**!

<br>
* 조건문의 기본 형태

```javascript
if (조건1){
} // 조건1이 통과할 경우 
else if (조건2){
	// 조건1이 통과하지 않고
	// 조건2가 통과할 경우
} else{
	// 모든 조건이 통과하지 않는 경우
}
```
조건에는 **Boolean으로 결과가 나오는 표현식**이 들어간다.

----
* 두 가지 조건이 한 번에 적용되는 경우의 조건문 
	* **논리 연산자(Logical Operator)** 사용
		* 학생이면서, 여성일 때 
			 `isStudent && isFemale` ( AND 연산자)
		* 학생이거나, 여성일 때 
			`isStudent || isFemale` (OR 연산자)
		* 학생이 아니면서, 여성일 때 
			`!isStudent && isFemale` (NOT 연산자)
			* truthy, falsy 여부를 반전시킨다.

* 논리 연산자 정리

|기호| 뜻 |
|:---:|:---:|
|`&&`|AND|
|`!`|NOT|
|`||`|OR|

<br>

* 기억해야할 6가지의 Falsy 값
	* 아래 6개는 if문에서 false로 변환되서 if 구문이 실행이 안 된다.
>
		1. false
		2. null
		3. undefined
		4. 0
		5. NaN
		6. '  '

<br>
<br>
<br>

> Written with [StackEdit](https://stackedit.io/).
