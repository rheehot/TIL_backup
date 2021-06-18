# HTML TIL 01

2021년 6월 18일에 작성된 문서 입니다.
HTML 배운 내용을 정리했습니다.


## HTML

### HTML이란?
* HyperText Markup Language 의 약자.
* 웹 페이지의 툴을 만드는 마크업 언어
* 웹 문서를 구조적으로 표현하기 위한 언어

### HTML의 사용 방법?
* HTML은 tag들의 집합이다.
	* Tag : 부등호(<>)로 묶인 HTML의 기본 구성 요소
*  html 확장자 사용

<br>

### HTML Tree Structure
* HTML 문서의 시작
	* html
		* head
			* title : Page title
		* body
			* h1 : Hello world
			* div : Contents here
				* span : Here too!

* 위의 구조를 실제 코드로 나타내 보자!
```html
<!DOCTYPE  html>  <!--이 문서가 html문서임을 명시-->
<html>  <!--html : 시작 태그 (문서의 전체 툴을 구성)---->
	<head>  <!--head : 문서의 메타 데이터를 선언-->
		<title>Page title</title>  
		<!--title : 문서의 제목, 브라우저 탭에 보임-->
	</head>  <!--</태그이름>은 해당 태그가 끝남을 의미-->
	<body>  <!--body : 문서의 내용을 담는 곳-->
		<h1>Hello World</h1>  
		<!--h는 heading. 크기 따라 h1부터 h6까지-->
		<div>Contents here 
		<!--div: content division 줄바꿈됨-->
			<span>Here too!</span>  
			<!--span : 줄바꿈이 없는 content 컨테이너-->
		</div>
	</body>
</html>
```

이 코드를 실제로 실행 시켜보면 아래와 같은 결과가 나온다.

<img width="389" alt="스크린샷 2021-06-18 오전 10 29 22" src="https://user-images.githubusercontent.com/85002287/122505389-3a033700-d037-11eb-85e5-f9e852c1bd7c.png">


### Self Closing Tag

태그 내부에 내용이 없다면, (<tag></tag>와 같이 표현되는 경우) <tag/>와 같이 표현 가능하다. 아래는 예시다.
```html
<img src = "codestates-logo.png"></img>
<img src = "codestates-logo.png"/>
```

<br>

---

### 많이 쓰이는 TAG들 모음

|태그|설명|
|:---|:--|
|`<div>`|Division|
|`<span>`|Span|
|`<img>`|Image|
|`<a>`|Link|
|`<ul>`&`<li>`|Unordered List|
|`<input>`|Input (Text,Radio,Checkbox)|
|`<textarea>`|Multi-line Text input|
|`<button>`|Button|

<br>

---
### `div` VS `span`



* `div` : 한 줄을 꽉 차지한다.
* `span` : 컨텐츠의 크기만큼의 공간을 차지한다.

(비교 결과는 아래에!)

<img width="804" alt="스크린샷 2021-06-18 오전 10 46 30" src="https://user-images.githubusercontent.com/85002287/122505478-63bc5e00-d037-11eb-8e55-015076b9ccf0.png">
<img width="817" alt="스크린샷 2021-06-18 오전 10 46 36" src="https://user-images.githubusercontent.com/85002287/122505487-6919a880-d037-11eb-8a0a-25248b0a2277.png">


### `img` : 이미지 삽입
```html
<img  src="https://i.imgur.com/JVAj4t0.jpg">
```
(결과는 아래에!)

<img width="183" alt="스크린샷 2021-06-18 오전 10 50 58" src="https://user-images.githubusercontent.com/85002287/122505533-83538680-d037-11eb-8ef5-1fa8304d7e06.png">

### `a` : 링크 삽입
```html
<a  href="https://codestates.com" target="_blank">코드스테이츠</a>
```
여기서 `target="_blank"`는 새 탭에서 열린다는 뜻.
a는 anchor(닻)의 약자. 하이퍼링크를 표시할 때 쓰임.

(결과는 아래에!)

<img width="296" alt="스크린샷 2021-06-18 오전 10 51 23" src="https://user-images.githubusercontent.com/85002287/122505573-98c8b080-d037-11eb-8ffb-ed9df8dd1c72.png">


### `ul,li` : 리스트
```html
<ul>
	<li>Item 1</li>
	<li>Item 2</li>
	<li>Item 3 has nested list
		<ul>
			<li>Item 3-1</li>
		</ul>
	</li>
</ul>
```
`ul`은 순서가 정해져있지 않은 리스트, `ol`은 순서가 있는 리스트다.

(결과는 아래에!)

<img width="515" alt="스크린샷 2021-06-18 오전 11 01 03" src="https://user-images.githubusercontent.com/85002287/122505588-a2eaaf00-d037-11eb-86d4-b6bd6506f945.png">

### `input, textarea` : 다양한 입력폼
```html
<input  type="text" placeholder="type here">
<div>
	<input  type="radio" name="choice" value="a">
	<input  type="radio" name="choice" value="b">
</div>
<textarea></textarea>
<div>
	<input  type="checkbox" checked> checked
	<input  type="checkbox"> unchecked
</div>
```

(결과는 아래에!)

<img width="615" alt="스크린샷 2021-06-18 오전 11 01 59" src="https://user-images.githubusercontent.com/85002287/122505613-af6f0780-d037-11eb-9f4b-b38d01474f9e.png">
<img width="749" alt="스크린샷 2021-06-18 오전 11 02 16" src="https://user-images.githubusercontent.com/85002287/122505624-b269f800-d037-11eb-8f2e-ad360443cead.png">
<img width="643" alt="스크린샷 2021-06-18 오전 11 02 37" src="https://user-images.githubusercontent.com/85002287/122505630-b4cc5200-d037-11eb-8ba4-fec0a7558b07.png">
<img width="683" alt="스크린샷 2021-06-18 오전 11 02 56" src="https://user-images.githubusercontent.com/85002287/122505636-b72eac00-d037-11eb-8c4e-4f8acfe7e40e.png">


### `button` : 버튼
```html
<button>Submit</button>
```
(결과는 아래에!)

<img width="535" alt="스크린샷 2021-06-18 오전 11 03 08" src="https://user-images.githubusercontent.com/85002287/122505653-bf86e700-d037-11eb-88c9-bcef5741dc12.png">


### `script` : javascript 실행용

```html
<script src = "my-javascript.js"></script>
```


---

### HTML의 요소

`<p class = "paragraph">This is an apple</p>`

* 구성
	* 시작 태그 (opening tag) : `<p class = "paragraph">`
		* 속성 (attribute) : `class = "paragraph"`
	* 콘텐츠 (contents) : `This is an apple`
	* 종료 태그 (closing tag) : `</p>`

* html의 속성 (attribute)
	* attribute name : 속성의 이름 `class`
	* attribute value : 속성의 값 `paragraph`
<br><br>
> Written with [StackEdit](https://stackedit.io/).
