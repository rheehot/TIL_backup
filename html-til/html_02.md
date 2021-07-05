# HTML TIL 02

2021년 7월 5일에 작성된 문서1번 입니다.
HTML 배운 내용을 정리했습니다.
(사실 자바스크립트로 HTML을 건드는 부분이지만 HTML요소가 많이 등장해서 그냥 HTML로 넣었습니다.)
<br><br>
## HTML에 자바스크립트 적용하기

#### `<script>` 태그를 이용

```html
<script src="myScriptFile.js"></script>
<!--HTML과 같은 디렉토리의 myScriptFile.js 불러오기-->
```

* 웹 브라우저가 코드를 해석하는데 `<script>` 를 만나면, HTML 해석 일시정지 후, `<script>` 를 먼저 실행. 
* **`<script>` 요소는 등장과 함께 실행된다.**

<br>

#### `<script>` 태그를 추가하는 방법
**1. `<head>` 안쪽에 태그 추가**
```html
<head>
<script src="myScriptFile.js"></script>
</head>
<!--HTML 문서의 head 영역에 포함되는 script 요소-->
```
**2.  `</body>` 가 끝나기 전에 추가** 
```
<body>
<script src="myScriptFile.js"></script>
</body>
<!--HTML 문서의 body 영역 끝에 포함되는 script 요소-->
```

<br><br><br>

## HTML이 JavaScript에서는 어떻게 표현될까?

```html
<html>
  <body>
    <div id="nav">
      <div class="logo"></div>
      <div class="menu-wrapper">
        <div class="menu"></div>
        <div class="menu"></div>
        <div class="menu"></div>
        <div class="profile-photo"></div>
      </div>
    </div>
    <div id="news-contents">
      <div class="news-content-wrapper">
        <div class="news-picture"></div>
        <div class="news-title"></div>
        <div class="news-description"></div>
      </div>
    </div>
    <div id="footer"></div>
  </body>
</html>
```
### Q1 - 자식 엘리먼트 찾기
> **body 엘리먼트의 자식 엘리먼트(element)는 총 몇 개인가요?**

**총 3개다. id가 `nav`, `news-contents`, `footer` 인 엘리먼트다.**

<br>

>자바스크립트에서 **DOM은 `document` 객체에 구현**되어 있다. 
브라우저에서 작동되는 자바스크립트 코드에서는, **어디서나 `document` 객체를 조회할 수 있다.** 

#### DOM 구조를 조회할 때에는 `console.dir` 

* **`console.dir`** : `console.log` 와 달리 **DOM을 객체의 모습으로** 출력. 

```javascript
console.dir(document.body)
// 출력된 객체를 통해 body의 자식 요소들을 찾을 수 있다.
// nav, news-contents, footer가 자식으로 확인
// 물론 document.body.childeren으로도 바로 조회 가능.
```
<br><br>
### Q2 - 부모 엘리먼트 찾기

> class의 이름이 news-contents 인 div 엘리먼트의 부모 엘리먼트는 무엇인가요?

**`body`엘리먼트는 id가 `news-contents` `div` 엘리먼트의 부모 엘리먼트다.** 


* id가 `news-contents` 인 엘리먼트를 조회하려면, `document.body.children` 의 첫 번째 엘리먼트를 조회한다.

>`document.body` 의 `children`을 조회할 때, 매번 `document.body` 부터 찾아가는 일은 번거로워 **따로 변수 선언을 해서 이 정보를 저장해두면, 주소를 참조하기때문에 언제든지 접근할 수 있다.** 

```javascript
let newsContents = document.body.children[1];

// document.body.children의 첫 번째 엘리먼트를 조회
// 변수 newsContents를 선언 
// id가 `news-contents`인 엘리먼트 할당.
```

<br><br>

* **`document.body.parentElement`** : **`body`의 부모 엘리먼트를 가리킴.**

```javascript
document.body.parentElement
// 부모 엘리먼트를 가리키는 속성이다
```




<br><br><br>

> Written with [StackEdit](https://stackedit.io/).
