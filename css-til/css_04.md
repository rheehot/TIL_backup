# CSS TIL 04

2021년 6월 30일에 작성된 문서 입니다.
CSS 배운 내용을 정리했습니다.

---
Selector 퀴즈 토대로 정리
(물론 모든 셀렉터를 넣진 못해서 일부 자름)

|이름|기능|코드|
|:---|:---|:---|
|셀렉터|스타일 적용하려고 HTML 요소 특정|`h1 { }`|
|전체 셀렉터|HTML 모든 요소 선택.|`* { }`|
|Tag 셀렉터|지정된 태그명을 가지는 요소 선택|`section, h1 { }`|
|ID 셀렉터|id값 선택|`#only { }`|  
|class 셀렉터|class값 선택|`.center { }`|
|attribute 셀렉터|지정 속성값 가지는 모든 요소 선택|`a[href] { }`|
|후손 셀렉터|셀렉터의 모든 **후손 요소 중 특정 셀렉터와 일치하는** 요소 선택|`header h1 {}`|
|자식 셀렉터|셀렉터의 모든 **자식 요소 중 특정 셀렉터와 일치하는** 요소|`header > p { }`|    
|인접 형제 셀렉터|셀렉터의 **형제 요소 중 셀렉터 바로 뒤**에 위치하는 특정 셀렉터 요소 선택|`section + p { }`|
|형제 셀렉터|셀렉터의 **형제 요소 중 셀렉터 뒤에 위치**하는 특정 셀렉터 요소 모두 선택|`section ~ p { }`|
|가상 클래스|가상 클래스를 임의로 지정하여 선택|`a:link { }`|
|요소 상태 셀렉터|해당 요소의 상태를 선택|`input:checked + span { }`|   
 |구조 가상 클래스 셀렉터|특정 순서인 자식 요소 선택|` p:first-child { }`|
 |부정 셀렉터|셀렉터에 해당하지 않는 모든 요소 선택|`div:not(:nth-of-type(2)) { }`|
 |정합성 확인 셀렉터|정합성을 확인|`input[type="text"]:valid { }`|
   


## HTML 구성

>CSS로 화면을 구분할 때에는 수직분할과 수평분할을 차례대로 적용하여 콘텐츠의 흐름을 따라 작업을 진행합니다.

* **수직분할** : 화면을 수직으로 구분, 콘텐츠가 가로로 배치될 수 있도록 요소 배치
* **수평분할** : 분할된 요소를 수평으로 구분, 내부 콘텐츠가 세로로 배치되도록 요소 배치.
    -  **수평으로 구분된 요소에 height 속성을 추가**하면, **수평분할을 보다 직관적으로** 할 수 있다.
    

  

## 레이아웃 리셋



-   박스 시작을 정확히 (0,0)에서 시작하고 싶은데, `<body>` 태그가 가진 기본 스타일에 약간의 여백이 있는 경우
-   width, height 계산이 여백을 포함하지 않아 계산에 어려움이 있는 경우
-   브라우저마다 기본 스타일이 조금씩 다른 경우


```css
// 기본 스타일링을 제거하는 CSS 코드

* {
  box-sizing: border-box;
}

body {
  margin: 0;
  padding: 0;
}
```

<br><br><br>

## Flexbox로 레이아웃 잡기

>박스를 유연하게 늘리거나 줄여 레이아웃을 잡는 방법. 

<br>

### display: flex 

* 부모 박스요소에 **`display: flex`로 자식 박스의 방향과 크기 결정**. 
* `display: flex`가 적용된 **자식 요소는 왼쪽부터 차례대로 배치**.

```html
<div id="outer">
  <div class="box">box1</div>
  <div class="box">box2</div>
  <div class="box">box3</div>
</div>
```

```css
#outer { // 자식 요소인 box들은 왼쪽부터 배치됨.
  display: flex;
  border: 1px dotted red;
  padding: 10px;
}

.box {
  border: 1px solid green;
  padding: 10px;
}
```  
<br>

### flex-direction 방향 지정

* flexbox는 박스의 **수직 분할이 기본**값. 
	* 방향을 설정해주면, 수평으로 분할 가능. 
* **`flex-direction` 속성은 부모 박스요소에** 적용. 
	* 자식 박스에 특정 속성을 안줘도, 부모 요소에 의해 자식 요소가 영향 받음. 

#### 주의사항

-   **`display` 속성에 `flex` 적용하는 것은 부모 요소에** 적용. (`display: flex`)
-   **자식 요소는 `flex`라는 속성에 값 적용**. (`flex: 0 1 auto`)

<br><br>

## grow(팽창 지수), shrink(수축 지수), basis(기본 크기)

* 자식 박스에 어떤 속성도 안주면, 왼쪽부터 오른쪽에 콘텐츠 크기만큼 배치. 

```css
flex: 0 1 auto; 
// 자식요소에 flex 속성을 추가하지 않으면 적용되는 기본값
```

<br>

flex 속성에 적용되는 세 가지는 **기본 크기를 바탕으로 필요에 따라 늘리거나 줄일 수 있는** 값이 적용. 

```
flex: <grow> <shrink> <basis>
// flex 속성에 적용되는 세 가지 값의 종류
```

<br>

>**이 순서와 기본값은 반드시 기억하세요. 
>flex: grow shrink basis
>flex: 0 1 auto**

<br>

* flex에 적용되는 **grow, shrink, basis도 각 값을 따로 지정 가능.**

```css
flex-grow: 0;
flex-shrink: 1;
flex-basis: auto;

// flex에 입력되는 세 속성을 따로 입력할 수도 있다.
```

<br>

* **grow, shrink** 속성은 단위가 없고, **비율에 따라 결과가 달라짐**. 

* **부모 박스 안에 n개의 자식 박스**가 있다 가정. 
	* 각 자식 박스가 갖는 **grow값의 총 합이 n**이면, **grow 속성의 값을 1로 설정하는 것은 1/n 가로 또는 세로를 적용**한다는 의미. (**비율!**)


```html
<div id="outer">
  <div class="box target">.box.target</div>
  <div class="box">.box</div>
  <div class="box">.box</div>
</div>

// html 파일에서, 자식 박스 요소 중 
// 첫 번째 자식 박스 요소에 target 클래스를 추가합니다.
```

<br><br>


## grow: 자식 박스는 얼마나 늘어날까?

* target 클래스를 가지고 있는 첫 번째 자식박스는, **부모 박스의 가로 길이 중에서 남은 빈 영역만큼 늘어남.** 
* **전체 자식요소가 가진 grow 값의 합은 1+0+0 = 1**이므로, **target 클래스를 가지고 있는 자식 박스의 가로 크기는 1/1 = 100%** 입니다. 
	* **(전체를 1이라 생각하고 비율만큼 나눠가진다고 생각하자.)**
* 다른 자식 박스안의 콘텐츠가 담긴 길이를 제외한 나머지 가로 길이가 target 클래스를 가진 자식박스의 가로 길이.

```css
.target { // flex: 0 1 auto가 기본값!
  flex: 1 1 auto;
}
// target 클래스에 flex-grow 속성의 값을 1로 설정
```

<br>

* box 클래스의 **`flex-grow`는 기본값인 0**. 
* 만약 **box 클래스의 `flex-grow` 값을 1로 하면, 모든 박스가 늘어나려**고한다. 
* 결과적으로 **모든 박스가 동일한 비율로 가로 길이가 늘어난다**. 
	* 총 grow 값 1+1+1, 각 박스는 1/3씩 크기를 가짐

```css
.box { // flex: 0 1 auto가 기본값!
  flex: 1 1 auto;
}
// box 클래스의 flex-grow 속성의 값을 1로 설정
```


 <br>

* **`flex-grow` 속성에 적용하는 값은 비율**을 의미. 
* 모든 자식 박스의 flex-grow 속성이 0보다 큰 값을 동일하게 가지는 경우, 각 박스의 가로 길이는 동일한 비율을 가짐. 

```css
.box {
  flex: 1 1 auto;
  /*
  flex: 2 1 auto;
  flex: 3 1 auto;
  flex: 4 1 auto;
  */
}

// 모든 자식 박스에 flex-grow 속성의 값을 동일하게 적용하면, 
// 모든 자식 요소의 flex-grow 속성의 값을 1로 설정한 것과 같다.
```
<br>

* box 클래스의 `flex-grow` 속성에는 1을 그대로 두고, target 클래스의 `flex-grow` 속성의 값을 변경. 
* target 클래스를 가지고 있는 자식 박스는, 다른 자식 박스와의 비율만큼 크기가 더 커집니다.

```css
.box {
  flex: 1 1 auto;
}

/* 
 * 자식 박스가 총 세개인데, target만 2의 비율을 가짐.
 * 2(target) + 1(box2) + 1(box3) = 4 
 * target의 비율은 50%.
 */
 
.target {
  flex: 2 1 auto;
}
// target 클래스의 flex-grow 속성을 2로 설정
```

* target 클래스에 적용된 flex-grow 속성의 값이 1, box 클래스에 적용된 flex-grow 속성의 값이이 1일 경우, grow가 적용된 전체 값은 `1+1+1 = 3`. 따라서, 각 자식 박스의 가로 길이는 1/3의 길이.


* target 클래스의 flex-grow 속성의 값이 2, box 클래스의 flex-grow 속성의 값이 1일 경우, grow가 적용된 전체 값은 `2+1+1 = 4`. 따라서, target 클래스를 가지지 못한 나머지 자식 박스는 1/4의 길이.


<br><br>
  

## shrink: 자식 박스는 얼마나 줄어들까?

* **grow와 반대**로, **설정 비율만큼 박스 크기가 작아짐**. 

* **비율로 레이아웃을 지정**할 경우 `flex-grow` 속성 또는 `flex: <grow> 1 auto`와 같이 **`grow` 속성에 변화를 주는 방식 권장**. 
* **flex-grow 속성으로 비율을 변경하는 경우, flex-shrink 속성은 기본값인 1로 두어도 무방.**

<br><br>

## basis: 이 박스의 기본 크기는?

* **자식 박스가 flex-grow나 flex-shrink에 의해 늘어나거나 줄어들기 전에 가지는 기본 크기.** 
* **flex-grow가 0일 때, basis 크기를 지정하면 그 크기는 유지**.

```html
<div id="outer">
  <div class="left">메뉴</div>
  <div class="right">본문</div>
</div>
// HTML 파일에 작성된 메뉴와 본문이라는 두 가지 자식 박스
```

```css
/* grow를 0으로 설정해줘야 100px 이상으로 늘어나지 않는다. */
.left {
  flex: 0 1 100px;
}
/*왼쪽 메뉴 박스는 크기를 유지해야 하므로*/ 
/*flex-basis 속성에 100px을 적용*/

/* 우측 박스는 grow를 1로 설정해 나머지 공간을 채움 */
.right {
  flex: 1 1 auto;
}
```


* **flex-grow 속성의 값이 0인 경우만 flex-basis 속성 값이 유지.** 
* diplay 속성에 flex가 적용된 컨테이너 내부에 존재하는 자식 박스는 경우에 따라, **basis로 설정된 크기가 항상 유지되는 것은 아니다.**
	 * flex-grow 속성의 값이 1 이상인 경우, flex-basis 속성에 적용한 값보다 커질 수도 있다. 



#### 참고

-   `width`와 `flex-basis`를 동시에 적용하는 경우, `flex-basis`가 우선
-   콘텐츠가 많아 자식 박스가 넘치면, `width`가 정확한 크기를 보장 못함.
-   (`flex-basis`를 사용하지 않는다면) 콘텐츠가 많아 자식 박스가 넘칠 경우를 대비해, `width` 대신 `max-width`를 쓸 수 있다.

  
  <br><br><br>

## 콘텐츠 정렬 방법

**axis(축)는 main axis 와 cross axis로 구분**

* **main axis**: **`flex-direction` 속성에 의해서 결정**. 
	* `flex-direction` 기본 값인 `row`면 main axis 는 가로축.

* **cross axis**: **여러 개의 main axis와 수직**을 이루는 방향. 
	* main axis가 가로일 때 cross axis는 세로

* **axis 기준으로 정렬**할 수 있는 속성: **`justify-content`, `align-items`** 
	* **`justify-content`: main axis**를 기준으로 정렬
	* **`align-items` : cross axis**를 기준으로 정렬.

<br><br>

### 콘텐츠 수평 정렬 (justify-content)

부모 박스에 **justify-content 속성을 적용하면, 자식 박스를 수평으로 정렬.** 

-   flex-start
-   flex-end
-   center
-   space-between

<br>

### 콘텐츠 수직 정렬 (align-items)

부모 박스에 **align-items 속성을 적용하면, 자식 박스를 수직으로 정렬.**

-   flex-start
-   flex-end
-   center
-   stretch

<br><br><br>


> Written with [StackEdit](https://stackedit.io/).
