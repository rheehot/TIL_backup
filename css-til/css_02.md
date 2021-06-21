﻿# CSS TIL 02

2021년 6월 21일에 작성된 문서 2번 입니다.
CSS 배운 내용을 정리했습니다.
(하나에 다 쓰기엔 내용이 길어져 문서 3개로 나누었습니다.)


## CSS
### 텍스트를 꾸며보자

### 색상

* **글자 색상 변경 속성 :  `color`** 
* 속성값 : HEX (16진수로 RGB 표현된 값) 또는 주요 색상의 이름

```css
.red {
  color: #ff0000; 
  /* red class의 color 속성에 #ff0000 할당 */
}
```

배경 색상, 박스 테두리 색상 적용

```css
.box {
  color: #155724; /* 글자 색상 */
  background-color: #d4edda; /* 배경 색상 */
  border-color: #c3e6cb; /* 테두리 색상 */
}
```

**글자, 배경, 테두리의 색상은 각기 다른 속성 가짐!**

<br><br>

---

###  글꼴

* **글꼴(폰트) 속성: `font-family`**

```
.emphasize {
  font-family: 
  "SF Pro KR", "MalgunGothic", "Verdana";
}
```

**글꼴 이름 : 따옴표 붙여서 적용**

* **fallback** : 표현하고 싶은 글꼴이 없거나 사용할 수 없는 경우를 위한 대비책
* fallback을 위해 여러 글꼴을 사용하는 경우 : 쉼표로 구분 
* 입력된 순서대로 fallback이 적용됩니다.  
  
  
  ----
  
### 크기

* **글자 크기 변경 :  `font-size` 속성 사용**

```css
.title {
  font-size: 24px; /*글자 크기를 24px로 적용*/
}
```
  
  <br>

####  알아야 할 몇가지 단위

글꼴의 크기에서는 **단위**가 무엇보다 중요 
글꼴의 단위 : 
-   절대 단위: px, pt 등
-   상대 단위: %, em, rem, ch, vw, vh 등



1.  여러 환경에 영향을 받지 않는 **절대적 크기**로 정하는 경우
    -   `px`(픽셀) 사용. 
    - px: 
	    - 글꼴 크기 고정 단위 (사용자 접근성이 불리). 
	    - 화면의 사이즈가 정해진 경우에 유리
2.  **일반적**인 경우
    -   상대 단위 `rem` 사용.
    -  `rem` : 
	    - 브라우저의 기본 글자 크기는 1rem (조절해서 사용 가능) 
	    - 사용자 설정한 기본 글꼴 크기를 따라서 접근성에 유리. 
	    - (`em`은 부모 엘리먼트 따라 크기가 변경되므로 계산이 어렵지만  `rem`은 root의 글자 크기에 따라서만 상대적으로 변함.)
3.  **반응형 웹(responsive web)에서 기준점**을 만들 때
    -   반응형 웹 : 디바이스 너비 따라 유동적 레이아웃이 적용되는 웹사이트
    -  디바이스 크기 별, CSS 달리 적용해야함. (디바이스 크기 기준: `px`) 

4.  화면 너비나 높이에 따른 **상대적인 크기가 중요한 경우**
    -    `vw`, `vh` 사용 (viewport width, viewport height)
    -  웹사이트가 보여지는 영역: Viewport 

<br>

---

### 기타 스타일링

텍스트를 꾸밀 때 자주 쓰는 속성들

-   굵기: `font-weight`
-   밑줄, 가로줄: `text-decoration`
-   자간: `letter-spacing`
-   행간: `line-height`

---

### 정렬

* 가로 정렬 : `text-align`을 사용
	* 유효한 값 : `left`, `right`, `center`, `justify`(양쪽 정렬)

* 세로로 정렬할 경우 : `vertical-align` 속성 
	* 이 속성은 부모 요소의 `display` 속성이 반드시 `table-cell`이어야 
	* 세로 정렬 : `정렬하려는 글자 둘러싼 박스 높이 > 글자 높이` 때만 가능
	
---

### `<center>` `<font>` 쓰지 말아야 하는 이유

* HTML의 초기에는, 스타일을 별개로 정의한다는 컨셉이 없었다. 
	* `<center>가운데 정렬</center>` 
	*  `<font color="#ff0000">빨간 글자</font>`와 같이 사용

* 지금은 [**관심사 분리**] 패러다임을 적용해 더이상 이 태그(`<center></center>`, `<font></font>`)를 사용하지 않는다. 
	* HTML 파일: 구조 설계 
	* CSS 파일: 스타일링 담당

<br><br>

> Written with [StackEdit](https://stackedit.io/).
