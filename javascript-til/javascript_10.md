# JavaScript TIL 10

2021년 7월 6일에 작성된 문서입니다.
javascript 배운 내용을 정리했습니다.


## 이벤트 객체 (POS기)


 >화면에 아메리카노와 카페라떼를 선택하도록 하는 두 개의 버튼이 있습니다. 이 두 개의 버튼을 클릭할 때, 각각 `아메리카노를 클릭하셨습니다.` 또는 `카페라떼를 클릭하셨습니다.` 라고 출력하는 단순한 프로그램입니다.

![POS기를 만드는 과정 일부](https://s3.ap-northeast-2.amazonaws.com/urclass-images/COFyepkA--1615450739986.gif)


```javascript
let menus = document.querySelectorAll("button"); 
//모든 버튼을 가져옴.

let btnAmericano = menus[0];
let btnCaffelatte = menus[1];

btnAmericano.onclick = handleClick;
btnCaffelatte.onclick = handleClick; 

function handleClick() {
  let currentMenu = // 사용자가 클릭한 버튼의 textContent 
					// 또는 innerHTML을 이용해 가져오기.
  console.log(currentMenu + "를 클릭하셨습니다.");
}
```

* **두 버튼의 이벤트 핸들러가 동일한 함수에 의해 동작**한다. 
	* 메뉴가 추가되더라도, 하나의 함수를 추가하면 된다. 
	* 함수를 작성하면 **함수를 여러 번 재사용할 수 있다**.

<br>

* 현재 메뉴의 이름을 가져오는 방법은 무엇일까요?
	* 버튼을 클릭하면, 그 버튼의 `textContent`(또는 `innerHTML`)을 이용해 메뉴의 이름을 가져올 수 있다. 

<br>


* 사용자가 **누른 버튼 따라 출력값이 달라져, 클릭된 이벤트 객체에서 메뉴의 이름을 가져온다**. 
	* **이벤트 객체 : 사용자 입력(`onclick`, `onkeyup`, `onscroll` 등)으로 발생한 이벤트 정보를 담은 객체.**

```javascript
function handleClick(event) {
  console.log(event); // 이벤트 객체에 담긴 모든 요소가 출력됨
  
  console.log(event.target)//버튼을 클릭했을때의 요소가 출력됨 
  //<button>아메리카노</button> 이런 식
  //메뉴가 button태그에 담겨있음을 알 수 있다.
  
  console.log(event.target.textContent);
  //사용자가 클릭한 메뉴명이 출력됨
}
```



<br>
<br>
<br>


> Written with [StackEdit](https://stackedit.io/).
