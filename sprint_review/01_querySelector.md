# Sprint 01_querySelector

2021년 6월 21일에 작성된 문서 입니다.
스프린트 내용을 정리했습니다. 



## Achievement Goals

>네이버 뉴스의 제목을 **querySelector와 textContent를 이용해 텍스트를 조회하고 변경**할 수 있다.

**querySelector, textContent**

-   `document.querySelector`를 이용해 웹 페이지의 특정 요소를 선택할 수 있다.
-   `textContent`를 이용해 선택한 엘리먼트의 Content를 조회할 수 있다.
-   `textContent`를 이용해 선택한 엘리먼트의 Content를 변경할 수 있다.

<br>

## document.querySelector( )

>`Document.querySelector()`는 **제공한 선택자 또는 선택자 뭉치와 일치하는 문서 내 첫 번째 `Element`를 반환**합니다. **일치하는 요소가 없으면 `null`을 반환**합니다. 

<br>

```javascript
document.querySelector(selector);
```
<br>

* html 클래스 이름이나 태그를 가져 오려고 querySelector 을 많이 사용
* CSS의 특정 선택자(Selector)를 가진 첫번째 요소를 선택하는 메소드
* `selector` : 유효한 CSS 선택자여야만 하며 아닐 경우  `SYNTAX_ERR` 에러 발생.
* selectors는 문서 전체에서 일치하는 엘리먼트를 갖고 오며, 이후 이 엘리먼트를 이용해 자손 엘리먼트들을 다시 갖고 올 수 있다.

ex)
아래 예제는 문서에서 "`myclass`"라는 클래스를 사용하는 첫 번째 요소 반환

```javascript
var el = document.querySelector(".myclass");
```

<br><br>
## textContent


* `textContent`는 텍스트를 추가할 수 있다.
  
 ```javascript 
element.textContent = '내용'  
  ```
* `textContent`는 어떤 텍스트를 가지고 있는지 알 수 있다.
* `textContent`는  `<script>`와  `<style>` 요소를 포함한 모든 요소의 콘텐츠를 가져온다. 

<br><br>

> Written with [StackEdit](https://stackedit.io/).
