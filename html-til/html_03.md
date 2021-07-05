# HTML TIL 03

2021년 7월 5일에 작성된 문서 2번 입니다.
HTML 배운 내용을 정리했습니다.
(사실 자바스크립트로 HTML을 건드는 부분이지만 HTML요소가 많이 등장해서 그냥 HTML로 넣었습니다.)
<br><br>
## CREATE - createElement

#### 새로운 element를 만드는 방법 ( Create)

아래 codesandbox의 console 탭에서 예시 코드를 입력하여 document 객체의 createElement 메소드를 이용하여 div element를 만듭니다.

```javascript
document.createElement('div')
// 새로운 div element를 만듦

const tweetDiv = document.createElement('div')
새롭게 생성한 div element를 변수에 할당
```

* `createElement` 메소드로 **생성된 엘리먼트는 공중에 떠있는 상태**다. 즉, **DOM의 트리구조에서 아무것도 연결이 되어있지 않다**는 것이다.

<br><br>
## APPEND - append, appendChild

#### CREATE에서 생성한 `tweetDiv`를 트리 구조와 연결 (Append)

```javascript
const tweetDiv = document.createElement('div')
//변수 tweetDiv에 새로운 div 엘리먼트를 할당

document.body.append(tweetDiv)
// 변수 tweetDiv에 담긴 새로운 div 엘리먼트를 
// body 엘리먼트에 append(넣기)
```
* **`append` 라는 메소드를 사용해서, 변수 `tweetDiv` 를 `body` 에 넣는다.**

<br><br>
## READ - querySelector, querySelectorAll

#### DOM으로 HTML 엘리먼트 정보를 조회: `querySelector`의 첫 번째 인자로 셀렉터(Selector)를 전달하여 확인. (Read)

>셀렉터로는 HTML 태그(`"div"`), id(`"#tweetList"`), class(`.tweet`) 세 가지가 가장 많이 사용됩니다.



### querySelector

**`querySelector` 에 `'.tweet'` 을 첫 번째 인자로 넣으면, 클래스 이름이 `tweet` 인 HTML 엘리먼트 중 첫 번째 엘리먼트를 조회할 수 있다.**

```javascript
const oneTweet = document.querySelector('.tweet')
// querySelector로 클래스 이름이 tweet인 HTML 엘리먼트를 조회

const tweets = document.querySelectorAll('.tweet')
// querySelectorAll로 클래스 이름이 tweet 인 
// 모든 HTML 엘리먼트를 유사 배열로 받아온다.

const container = document.querySelector('#container')
const tweetDiv = document.createElement('div')
container.append(tweetDiv)
// tweetDiv를 container의 마지막 자식 요소로 추가

const getOneTweet = document.getElementById('container')
const queryOneTweet = document.querySelector('#container')
console.log(getOneTweet === queryOneTweet) // true
// getElementById와 querySelector로 
// 각각 받아 온 container는 하나의 요소
// querySelector와 비슷한 역할을 하는 오래된 방식
// 이전 버전의 브라우저 호환성으로 옛날 방식을 사용해야 할 수도 있다.
```
* **CREATE에서 생성한 div 엘리먼트를 `container`의 맨 마지막 자식 엘리먼트로 `tweetDiv`를 추가한다.**
  
  <br>

* 여러 개의 엘리먼트를 가져오기 위해서는, `querySelectorAll`  사용
* 이렇게 조회한 HTML 엘리먼트들은 **배열처럼** for문을 사용할 수 있다. 
>주의하세요! 앞서 조회한 **HTML 엘리먼트들은 배열이 아닙니다!** **이런 '배열 아닌 배열'을 유사 배열, 배열형 객체 등 다양한 이름으로 부릅니다.** 정식 명칭은 [Array-like Object]입니다. 

  <br><br>

## UPDATE - textContent, classList.add

#### 기존에 생성한 빈 `div` 태그를 업데이트하여, 보다 다양한 작업을 할 수 있다. (Update)

* **`textContent` 를 사용해 비어있는 `div` 엘리먼트에 문자열을 입력.**

```javascript
console.log(oneDiv) // <div></div>
oneDiv.textContent = 'dev';
console.log(oneDiv) // <div>dev</div>
// textContent를 이용해 문자열을 입력
```

* **CSS 스타일링이 적용될 수 있도록, `div` 엘리먼트에 `class`를 추가.**

``` javascript
oneDiv.classList.add('tweet')
console.log(oneDiv) // <div class="tweet">dev</div>
// classList.add를 이용해 'tweet' 클래스를 추가
```
  
* 이번에는 **`append`를 이용해 `container`의 자식 요소로 추가.**

```javascript
const container = document.querySelector('#container')
container.append(oneDiv)
// append를 이용해 container의 자식 요소에 oneDiv를 추가
// 새롭게 추가한 엘리먼트는 클래스 tweet의 스타일이 적용된 상태로 출력
```
<br><br>

## DELETE - remove, removeChild

#### 삭제하는 법 (Delete)

1. 먼저 **삭제하려는 엘리먼트의 위치를 알고 있는 경우** 

**`remove` 메소드를 사용**

```javascript
const container = document.querySelector('#container')
const tweetDiv = document.createElement('div')
container.append(tweetDiv)
tweetDiv.remove() // 이렇게 append 했던 엘리먼트를 삭제할 수 있다.

// id가 container인 엘리먼트 아래에 tweetDiv를 추가하고,remove로 삭제
// tweetDiv를 container의 자식으로 추가한 뒤, 삭제
```

<br>

2. 여러 개의 자식 엘리먼트를 지우는 방법

**`innerHTML` 을 이용해 모든 자식 엘리먼트를 지운다.** 

```javascript
document.querySelector('#container').innerHTML = '';
// id가 container인 엘리먼트 아래의 모든 엘리먼트를 지운다.
```
  

>`innerHTML` 을 이용하는 방법은 분명 간편하고 편리한 방식이지만, innerHTML은 보안에서 몇 가지 문제를 가지고 있습니다. 

<br>

**`removeChild` 는 자식 엘리먼트를 지정해서 삭제하는 메소드. 
(`innerHTML 대신 사용`)**

```javascript
const container = document.querySelector('#container');
while (container.firstChild) {
  container.removeChild(container.firstChild);
}
// container의 첫 번째 자식 엘리먼트가 존재하면, 
// 첫 번째 자식 엘리먼트를 제거
// 엘리먼트가 남아있지 않을 때까지, 첫 번째 자식 엘리먼트를 삭제
```
>`removeChild` 와 `while` 을 이용해 자식 요소를 삭제하면, 제목에 해당하는 H2 "Tweet List"까지 삭제됩니다. 

<br>

#### Tweet List까지 삭제되는 것을 방지하기 위한 방법

1. **자식 엘리먼트를 하나만 남기기** 

```javascript
const container = document.querySelector('#container');
while (container.children.length > 1) {
  container.removeChild(container.lastChild);
}
// container의 자식 엘리먼트가 1개만 남을 때까지, 
// 마지막 자식 엘리먼트를 제거
```

  
**2. 직접 클래스 이름이 `tweet`인 엘리먼트만 찾아서 지우기**

```javascript
const tweets = document.querySelectorAll('.tweet')
tweets.forEach(function(tweet){
    tweet.remove();
})
// or
for (let tweet of tweets){
    tweet.remove()
}
// 클래스 이름이 tweet인 엘리먼트만 찾아서 제거
```








<br><br>


> Written with [StackEdit](https://stackedit.io/).
