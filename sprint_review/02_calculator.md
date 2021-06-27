# Sprint 02_calculator

2021년 6월 26일에 작성된 문서 입니다.
스프린트 내용 중 **Bare Minimum Step3 부분 (기본 계산 기능 구현)** 을 정리했습니다. 


---

-   연산 시  `script.js`의  `calculate`  함수를 활용할 수 있도록 함수  `calculate`를 작성합니다. **(사칙연산 담당 부분)**
	* 조건문으로 작성해서 사칙 연산을 구현하는 부분이었다.

```javascript
function  calculate(n1,  operator,  n2)  {

let result =  0;
// TODO : n1과 n2를 operator에 따라 계산하는 함수를 만드세요.
// ex) 입력값이 n1 : '1', operator : '+', 
//     n2 : '2' 인 경우, 3이 리턴됩니다.

if(operator ===  "+"){
result = n1 + n2;  // 더하기 계산
}

else  if(operator ===  "-"){
result = n1 - n2;  // 빼기 계산
}

else  if(operator ===  "*"){
result = n1 * n2;  // 곱하기 계산
}

else result = n1 / n2;  // 나머지 나누기 계산

return  String(result);

}
```

<br>

-   숫자 버튼, 연산자 버튼, 숫자 버튼을 순서대로 클릭했을 때, 화면에 숫자, 연산자, 순자가 순서대로 나타나야 합니다. **(숫자와 연산자가 제대로 띄워졌는가)**
	* 이 부분도 조건문을 이용해야했다. 첫번째 숫자가 0으로 입력이 되어있을 경우, 즉 값이 없을 경우 첫번째 버튼 누른 것을 첫번째 숫자에 표시한다.
	* 이미 첫번째 숫자가 표시 되었다면 두번째 숫자 누른 것을 두번째 숫자에 표시한다.

```javascript
if (target.matches('button')) {
// TODO : 계산기가 작동할 수 있도록 아래 코드를 수정하세요. 
// 클릭된 HTML 엘리먼트가 button이면

if (action ===  'number') {
// 그리고 버튼의 클레스가 number이면
// 아래 코드가 작동됩니다.

console.log('숫자 '  + buttonContent +  ' 버튼');
if(firstOperend.textContent ===  '0'){
// 첫번째 숫자의 화면이 0일 경우
// 첫번째 숫자 누른 것을 채워라

firstOperend.textContent = buttonContent;  
// 처음 누른 버튼이 숫자
}  // 첫번째 숫자가 입력되는 경우

else
// 첫번째 문자열이 공백이 아닐 경우 즉 0이 아닌 다른 수가 채워져 있으면
// 두번째 숫자를 누른 것을 채우자.

secondOperend.textContent = buttonContent;  
// 두번째 숫자가 입력
// 두번째 숫자가 입력 되는 경우
}
```


<br>

-   숫자 버튼, 연산자 버튼, 숫자 버튼, 엔터 버튼을 순서대로 클릭했을 때, 화면에 숫자, 연산자, 숫자, =, 연산 결과가 순서대로 나타나야 합니다. **(계산이 제대로 되었나)**
	* 이 부분은 위에서 만들었던 `calculate`  함수를 호출해오는 과정이다.

```javascript
if (action ===  'calculate') {

calculatedResult.textContent =  
calculate(Number(firstOperend.textContent),
operator.textContent,
Number(secondOperend.textContent));

console.log('계산 버튼');
}
```



<br>

-   AC 버튼을 클릭했을 때, 화면에 0, +, 0, =, 0 이 순서대로 나타나야 합니다. **(초기화)**
	* 이 부분은 초기화한 값을 변수에 할당하는 부분이었다.

```javascript
if (action ===  'clear') {

console.log('초기화 버튼');

firstOperend.textContent =  0;
secondOperend.textContent =  0;
operator.textContent =  "+"; 
calculatedResult.textContent =  0;

}
```
---
#### 잘 되는지 확인하기


<br><br><br>


> Written with [StackEdit](https://stackedit.io/).
