# React TIL 01


2021년 7월 8일에 작성된 문서 1번 입니다.
React 배운 내용을 정리했습니다.

## JSX
### 자바 스크립트 문법의 확장판
* **리액트를 사용해서 UI 구성**시 사용
* 문자열도 아니고 그렇다고 HTML도 아님.

<br>

* JSX는 브라우저가 바로 실행할 수 있는 JavaScript 코드가 아니라서 **브라우저가 이해할 수 있는 JavaScript 코드로 변환을 해주어야**한다. 
  * 이때 이용하는 것이 **“Babel”**. 
  * Babel은 JSX를 브라우저가 이해할 수 있는 JavaScript로 컴파일한다. 

<br>

* **React**에서는 DOM과 다르게 **CSS, JSX 문법만을 가지고 웹 애플리케이션을 개발**할 수 있다. 
* **JSX를 사용하면 JavaScript만으로 마크업 형태의 코드를 작성하여 DOM에 배치할 수 있게 된다.**

<br>

### JSX의 장점

* React에서는 JSX를 이용해서 DOM 코드보다 **명시적으로 코드를 작성**할 수 있다. 
* JavaScript 문법과 HTML 문법을 동시에 이용해 **기능과 구조를 한눈에 확인**할 수 있다. 
* JSX없이 리액트 개발은 가능하지만 가독성도 떨어지고 복잡해지기만하므로 JSX를 사용한다.
```jsx
// JSX 없이 활용한 React
return  React.createElement("h1",  null,  `Hello, ${formatName(user)}!`);

// JSX 를 활용한 React
return <h1>Hello, {formatName(user)}!</h1>;

// 확실히 JSX쪽이 보기가 쉽고 복잡하지 않다.
```
<br>
<br>

## JSX의 규칙과 활용

* **여러 엘리먼트를 작성**하고자 하는 경우, 꼭 **opening tag와 closing tag**로 감싸주어야 한다. **(하나의 엘리먼트에 모든 엘리먼트가 포함)**

![](https://images.velog.io/images/heewonkim-dev/post/9982494b-d218-45b5-be82-17b09308ef9e/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-07-08%20%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB%2010.23.15.png)

<br>

* **CSS class 속성**을 지정하려면 **className**으로 표기한다. (class로 작성하게 된다면 React에서는 자바스크립트 클래스로 받아들임)

![](https://images.velog.io/images/heewonkim-dev/post/5588370a-2bd6-4bdf-bb12-8373943b6375/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-07-08%20%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB%2010.24.53.png)

<br>
* **JavaScript 표현식** 쓸 때는 **중괄호**를 이용한다. (중괄호를 사용하지 않으면 일반 텍스트로 인식함.)

![](https://images.velog.io/images/heewonkim-dev/post/f8e81298-22cd-459c-a8f7-7f845fd62664/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-07-08%20%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB%2010.26.45.png)

<br>

* **사용자 정의 컴포넌트**는 꼭 **대문자**로 시작하자. (소문자로 시작하게 되면 일반적인 HTML 엘리먼트로 인식)

![](https://images.velog.io/images/heewonkim-dev/post/834a94f2-e101-4da0-ac4a-6e88935a2095/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-07-08%20%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB%2010.36.42.png)

<br>

* **조건부 렌더링**은 if문이 아닌 **삼항연산자**를 이용해야한다.

![](https://images.velog.io/images/heewonkim-dev/post/142aa1a1-eda6-4305-ab3b-db2de33d1094/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-07-08%20%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB%2010.37.16.png)

<br>

* **여러 개의 HTML 엘리먼트**를 표시할 때는 **`map()`** 함수를 사용
  * map 함수를 사용할 때는 반드시 **"key" JSX 속성**을 넣어야한다.
  
  ![](https://images.velog.io/images/heewonkim-dev/post/73abb9b3-b6d4-4fa2-9eba-97edd9605917/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-07-08%20%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB%2010.38.30.png)

```jsx
export  default  function  App()  {
const  content  =  posts.map((posts)  =>  (
<div  key={posts.id}>
<h3>{posts.title}</h3>
<p>{posts.content}</p>
</div>
));
// 이렇게 써서 Hands-On의 에러가 사라졌다!
```

![](https://images.velog.io/images/heewonkim-dev/post/1c5fd483-9e74-4fab-8332-75f3f389b6d3/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-07-08%20%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB%2010.42.25.png)

<br>
<br>
<br>

> Written with [StackEdit](https://stackedit.io/).
