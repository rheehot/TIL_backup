# CSS TIL 03

2021년 6월 21일에 작성된 문서 3번 입니다.
CSS 배운 내용을 정리했습니다.
(하나에 다 쓰기엔 내용이 길어져 문서 3개로 나누었습니다.)


## CSS BOX MODEL

![layout_of_HTML](https://i.stack.imgur.com/bJKfH.png)

>모든 콘텐츠는 각자의 영역을 가지며, 일반적으로 하나의 콘텐츠로 묶이는 엘리먼트(요소)들이 하나의 박스가 됩니다.

* 박스는 항상 직사각형 
	* 너비(width), 높이(height) 가짐. 
	* CSS로 속성과 값을 이용해 그 크기를 설정

>박스가 **차지하는 영역을 시각적으로 확인**하기 위해 **배경색을 꼭 넣으세요!**

<br><br>

---

### 줄바꿈이 되는 박스(block) vs. 옆으로 붙는 박스(inline, inline-block)

* 박스 종류 : 줄바꿈 되는 박스 & 줄바꿈 없이 옆으로 붙는 박스
	* 줄바꿈 되는 박스: block 박스
	* 줄바꿈 없이 크기지정을 할 수 없는 박스: inline 박스
	* 줄바꿈이 일어나지 않는 동시에 block 박스의 특징을 가지는 inline-block 박스


#### Block Box element

![block](https://s3.ap-northeast-2.amazonaws.com/urclass-images/GbKsvsbQ6-1603449678641.png) 

 
#### Inline Box element 

![inline](https://s3.ap-northeast-2.amazonaws.com/urclass-images/8ko3GQGPi-1603676953415.png) 


* Block 요소: `<div>`, `<p>` 

* Inline 요소: `<span>`
	*  inline 박스 :
	CSS의 width, height 등 박스의 크기를 설정하는 속성이 적용 안 됨.
<br>

#### Inline-Block Box element 
다른 요소 옆에 붙으면서, 자체적으로 고유의 크기 가짐. 

![inline-block](https://s3.ap-northeast-2.amazonaws.com/urclass-images/cQSYoUtRu-1603449683236.png)

즉,
  
||block|inline-block|inline|
|:----|:----|:----|:----|
|줄바꿈 여부|줄바꿈이 일어남|줄바꿈이 일어나지 않음|줄바꿈이 일어나지 않음|
|기본적으로 갖는 너비(width)|100%|글자가 차지하는 만큼|글자가 차지하는 만큼|
|width, height 사용 가능여부|가능|가능|불가능|

---
### 박스의 구성요소

![Box_model](https://codinglead.github.io/images/box-model.png)

#### border (테두리)

심미적인 용도 + 개발 과정에서도 매우 의미있게 사용 
>각 영역이 차지하는 크기를 파악하기 위해, 레이아웃을 만들면서 그 크기를 시각적으로 확인할 수 있도록 만듭니다. 
``` css
p {
  border: 1px solid red; 
  /*테두리 실선 확인.*/
  /*p태그에 1px 빨간색 실선 추가*/
}
```
* `border` 속성에 적용된 값:
	* 테두리 두께(`border-width`)
	* 테두리 스타일(`border-style`)
	* 테두리 색상(`border-color`)
	* 괄호 안에 것들이 border 속성에 추가할 수 있는 세부 속성

-   테두리를 점선으로 만들 경우
	- `border-style`의 값 중 하나를 바꾸자.
-   둥근 모서리로 만들 수도 있습니다. 
	- `border` 속성만으로 둥근 모서리 만들 수 없다.
-   박스 바깥에 그림자 넣기
	- 그림자를 명확하게 보기 위해서는 `background`속성이 불투명해야함.

<br>

#### margin (바깥 여백)

```css
p {
  margin: 10px 20px 30px 40px;
  /*p태그 상하좌우에 여백을 추가*/
}
```

* 각각의 값 : `top`, `right`, `bottom`, `left` (시계 방향)
* margin: 주황색으로 표현
* 값을 하나만 넣으면 모든 방향의 바깥 여백에 적용 

```css
p { /*이 경우는 방향을 특정한 속성*/
  margin-top: 10px;
  margin-right: 20px;
  margin-bottom: 30px;
  margin-left: 40px;
  /*위치를 특정해 여백을 추가*/
}
```
* 이 규칙은 padding에도 동일하게 적용됨.

* 바깥 여백에 음수값을 지정 가능.
	*  다른 엘리먼트와의 간격이 줄어듦. 
	* 화면(viewport)에서 아예 사라지게 하거나, 다른 엘리먼트와 겹치게도 가능.

```css
p {
  margin-top: -2rem;
  /*p태그 margin-top 속성에 음수 값을 지정*/
}
```


  <br>

#### padding (안쪽 여백)

* border 기준으로 박스 내부의 여백 지정 
* 값 순서 따른 방향은 margin과 동일 (시계 방향)
* padding은 초록색으로 표현

```css
p {
  padding: 10px 20px 30px 40px;
  /*p태그의 padding 속성에 여백을 추가*/
}
```

>배경색이나 border를 적용하면, 안쪽 여백을 더욱 선명하게 확인할 수 있습니다.

```css
p {
  padding: 10px 20px 30px 40px;
  border: 1px solid red;
  background-color: lightyellow;
  /*p태그에 border, background-color 속성을 추가*/
}
```

<br><br>

---
  

### 박스를 벗어나는 컨텐츠 처리

* 박스 크기 < 콘텐츠 크기
	* 콘텐츠가 박스 밖으로 빠져나옴
	* 콘텐츠가 박스 밖으로 나가는 경우
		* 박스 크기에 맞게 콘텐츠를 더 이상 안 표시.
		* 박스 안에 스크롤을 추가

```css
p {
  height: 40px;
  overflow: auto;
  /*p태그에 overflow 속성을 지정.*/ 
  /*박스보다 큰 콘텐츠에 스크롤을 표시*/
}
```
* overflow 속성 `auto` : 콘텐츠가 넘치는 경우 스크롤 생성. 
* 콘텐츠의 내용을 보여주고 싶지 않을 경우, overflow 속성에 `hidden` 값을 사용. 
* overflow 속성: x축과 y축을 지정해 가로 방향으로 스크롤하거나 세로 방향으로 스크롤 할 수 있게 가능.
* `overflow-x` 속성과 `overflow-y` 속성을 이용 시, 두 방향을 모두 지정 가능.


<br>

---

### 박스 크기 측정 기준

>박스 크기를 측정하는 기준은 매우 중요

아래의 예시를 보자.
```html
<!--html 예시-->
<div id="container">
  <div id="inner">
    안쪽 box
  </div>
</div> 
```

```css
/*CSS 예시*/
#container {
  width: 300px;
  padding: 10px;
  background-color: yellow;
  border: 2px solid red;
}
#inner {
  width: 100%;
  height: 200px;
  border: 2px solid green;
  background-color: lightgreen;
  padding: 30px;
}
```

<br>

-   `#container`너비: 324px (300px이 아님) 
	- 브라우저는 다음과 같은 계산 실행
    
    ```
      300px (콘텐츠 영역)
    + 10px (padding-left)
    + 10px (padding-right)
    + 2px (border-left)
    + 2px (border-right)
    ```
    
-   `#inner`의 100%: 364px (300px이 아님) 
	- 브라우저는 다음과 같은 계산을 실행
    
    ```
      300px  (300px의 100%)
    + 30px (padding-left)
    + 30px (padding-right)
    + 2px (border-left)
    + 2px (border-right)
    ```
    
    
    <br><br>  
    

* 처음 레이아웃 디자인을 할 때 가장 많이하는 실수
	*  박스에 적용할 여백을 고려하지 않고 박스 크기 디자인 
	* 박스 크기를 디자인할 때 콘텐츠 영역만 고려 
		* 개발 과정에서 처음 생각한 레이아웃을 벗어날 수 있다. 
		* 여백을 고려하지 않은 계산방식은 레이아웃 디자인을 어렵게 한다.

* 레이아웃 디자인을 조금 더 쉽게하는 방법
	* **여백과 테두리 두께를 포함**한 **박스 계산 법**입니다. 
	* `*`: 모든 요소 선택 셀렉터 
	* 모든 요소를 선택해 `box-sizing` 속성 추가하고, `border-box`라는 값을 추가.

```css
* {
  box-sizing: border-box;
  /*모든 요소에 'box-sizing: border-box'를 추가*/
}
```
* 모든 요소에 `box-sizing: border-box` 적용 
	* 모든 박스에서 여백과 테두리를 포함한 크기로 계산 
	* `box-sizing`: HTML 문서 전체에 적용 
	* `box-sizing`을 일부 요소에만 적용하는 경우, 혼란을 가중 

<br>

>**앞으로 레이아웃과 관련된 이야기를 할 때에는 border-box 계산법을 기준으로 이야기합니다.** 박스 크기 측정 기준 두가지를 항상 염두해주세요.

<br>

* `content-box`: 는 박스 크기 측정 기본값

* **대부분의 레이아웃 디자인에서 여백과 테두리를 포함하는 박스 크기 계산법인 `border-box`를 권장**

![image](https://s3.ap-northeast-2.amazonaws.com/urclass-images/JaLXw3IKR-1618222003531.png)  

<br><br><br>
<br>


> Written with [StackEdit](https://stackedit.io/).
