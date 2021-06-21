# CSS TIL 01

2021년 6월 21일에 작성된 문서 1번 입니다.
CSS 배운 내용을 정리했습니다. 
(하나에 다 쓰기엔 내용이 길어져 문서 3개로 나누었습니다.)

## CSS
### CSS의 사용 목적
CSS는 스타일링을 담당

-   콘텐츠의 배치와 위치 (**레이아웃** 디자인)
-   텍스트를 강조하거나 밑줄을 치는 등, 최소한의 **타이포그래피** (Typography)
<br>

### 기본 문법을 알아보자!

#### CSS의 기본 구성 요소
![css_grammar](https://s3.ap-northeast-2.amazonaws.com/urclass-images/wEjk95H8v-1603449405224.png)

CSS의 구성 : 
1. 셀렉터(Selector) : 태그, id, 또는 클래스를 선택. (특정 요소 선택)
2. 선언 블록(Deeclaration Block) : 중괄호 안에서 이 요소에 적용할 내용 작성
	* 선언 : 요소에 적용할 수 있는 내용 (색상, 글자크기 etc)
		* 속성명 : 무슨 속성을 적용할 지를 말함
		* 속성값 : 속성에 적용할 값을 입력하여 스타일을 표현
		* 선언 구분자 : 세미콜론(;)을 사용

<br>

### CSS 파일 추가

CSS 파일을 HTML 파일에 연결:  `link` 태그 안 `href` 속성을 통해 연결

```javascript
<link rel="stylesheet" href="index.css" />
```  

* `link` : HTML 파일과 다른 파일을 연결
	* `rel` : 연결하고자하는 파일의 역할이나 특징 
	* CSS(Cascading Style Sheet)는 Style sheet ➡️ `rel`속성에 `stylesheet`을 추가
	* `href`속성에는 파일의 위치를 추가 
		* 한 폴더 내에 있는 경우, 파일이름만 입력
		* 다른 폴더에 파일이 존재하는 경우, 절대경로 또는 상대경로를 입력
<br><br>
---
### 셀렉터 (selector)

#### id로 이름 붙여서 스타일링 적용

**id**  : 스타일 지정 시, 한 가지만 지정해서 쓰는 이름 (**# 이름**)

`<h4>` 요소만 색을 바꾸려면? 
h4 요소는 하나의 태그! 태그를 선택해 색상을 변경 가능.

```css
h4 {
  color: red; /* h4 태그의 색상을 변경 */
}
```

navigation section 아래의 `<h4>` 요소를 **정확하게 선택하기 위해서는 이 엘리먼트에 id를 붙여**서 해결 
```css
#navigation-title {
  color: red; 
  /* navigation section의 h4만 콕 찝어 */
}
```
이름을 붙일 때는 가능한 의미를 담아서 구분할 수 있도록.

**id가 있는 요소를 선택할 때에는 `#`기호를 이용**. 
**id는 하나의 문서에서 한 요소에만 사용**.

<br><br>

---
### class로 스타일을 분류하여 적용하기


**class** : 그룹으로 묶어서 스타일을 지정 (**.이름**)

동일한 기능을 하는 CSS를 여러 요소에 적용하기 위해 사용 

모든 `li`요소에 동일한 class를 추가하면, 동일한 스타일을 여러 엘리먼트에 적용할 수 있습니다. 

class는 **`#`이 아닌 `.`을 이용해 선택.**

```html
<ul>
  <li class="menu-item">Home</li>
  <li class="menu-item">Mac</li>
  <li class="menu-item">iPhone</li>
  <li class="menu-item">iPad</li>
</ul>
```

```css
.menu-item {
  text-decoration: underline; 
  /* menu-item 클래스 */
}
```

**id나 class 이름은 자유지만 숫자로 시작해선 안 됨.**

<br><br>

---
### 여러 개의 class를 하나의 엘리먼트에 적용

**여러 class를 하나의 요소에 적용**하기 위해 **공백으로 적용하려는 class의 이름을 분리**

```html
<li class="menu-item selected">Home</li>
```

>요소를 만들거나, 요소에 스타일링 적용할 때 항상 이름과 목적이 일치하는지 잘 살펴보세요.
```css
.selected {
  font-weight: bold;
  color: #009999;
}
```
<br><br>

---
### id VS Class
|id | class|
|:---|:---|
|`#`으로 선택| `.`으로 선택|
|한 문서에 단 하나의 요소에만 적용| 동일한 값을 갖는 요소 많음|
|특정 요소에 이름을 붙이는 데 사용| 스타일의 분류(classification)에 사용|


<br><br>

> Written with [StackEdit](https://stackedit.io/).
