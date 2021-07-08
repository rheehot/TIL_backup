# React TIL 02

2021년 7월 8일에 작성된 문서 2번 입니다.
React 배운 내용을 정리했습니다.


<br>

## map을 이용한 반복 



### map을 이용한 반복

>배열 메소드 map의 특성을 다시 떠올려봅시다.
>
>-   **배열의 각 요소를**
>-   **특정 논리(함수)에 의해**
>-   **다른 요소로 지정(map)합니다.**

<br>

* 블로그 `posts`의 요소 : **id, title, content** 
* 브라우저에서 React로 보여주려면 여러 HTML 엘리먼트에 이 데이터를 적절히 넣어야한다. 

아래의 수도 코드를 보자.


> 수도 코드
> 
> 배열의 각 요소(post)를 특정 논리(postToElement 함수)에 의해 다른 요소로 지정(map) 합니다.

<br>

* **반복적으로 작성해야 하는 부분만 골라서 배열의 요소로** 넣으면 React가 이를 인지하고 모든 요소를 렌더링을 한다. 

```jsx
//React에서 방금 적은 수도코드를 코드로 쓰면 아래와 같다. 

function Blog() {
  const postToElement = (post) => (
    <div>
      <h3>{post.title}</h3>
      <p>{post.content}</p>
    </div>
  );

  const blogs = posts.map(postToElement);

  return <div className="post-wrapper">{blogs}</div>;
}
// 배열 메소드 map 활용
```



> **return 문 안에서 `map` 메소드를 사용할 수는 없을까요?** 사용할 수 있습니다. JSX를 사용하면 중괄호 안에 모든 표현식을 포함할 수 있기 때문에 map 메소드의 결과를 return문 안에 인라인으로 처리할 수 있습니다. 코드 가독성을 위해 **변수로 추출할지** 아니면 **인라인에 넣을지는** 개발자가 판단해야 할 몫입니다.

<br>
<br>


### key 속성

React에서 `map` 메소드 사용 시, **key 속성**을 넣지 않으면 에러가 뜬다. 
**key 속성**의 위치는 **`map` 메소드 내부에 있는 첫번재 엘리먼트**에 넣자.

![](https://s3.ap-northeast-2.amazonaws.com/urclass-images/uItGgUOES-1619325182771.png)


  <br>


> **key 속성 값이 반드시 id가 되어야 하나요? id가 존재하지 않으면 어떻게 해야 하나요?** key 속성값은 **가능하면 데이터에서 제공하는 id를 할당해야** 합니다. **key 속성값**은 id와 마찬가지로 **변하지 않고, 예상 가능하며, 유일해야** 하기 때문입니다. **고유한 id가 없는 경우에만 배열 인덱스를 넣어서 해결**할 수 있습니다. 배열 인덱스는 최후의 수단(as a last resort)으로만 사용합니다. 

<br><br>


* 아래의 key속성 값 할당의 올바른 예시를 참조해보자.

```jsx
// 바른 key 속성 값 할당의 예

function Blog() {
  // postToElement라는 함수로 나누지 않고 아래와 같이 써도 무방하다.
  const blogs = posts.map((post) => (
    <div key={post.id}>
      <h3>{post.title}</h3>
      <p>{post.content}</p>
    </div>
  ));
  return <div className="post-wrapper">{blogs}</div>;
}
```
![](https://images.velog.io/images/heewonkim-dev/post/1c5fd483-9e74-4fab-8332-75f3f389b6d3/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-07-08%20%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB%2010.42.25.png)


<br>
<br>

## 컴포넌트 기반 개발

#### 컴포넌트 : 하나의 기능을 구현하는 여러 종류의 코드 묶음이자, UI 구성 필수 요소.

* 컴포넌트를 여러개 만들고 조합해 어플리케이션을 만들 수 있다.

* 모든 리액트 애플리케이션은 최소 한 개의 컴포넌트를 가지고 있다 
  * **최상위 컴포넌트** : 근원(**root**)이 되는 역할 & **자식 컴포넌트**를 가질 수 있다. 
  * 이 계층적 구조(hierarchy)를 트리 구조로 형상화할 수 있다. (그림을 보면 이해가 더 빠를 것이다. 참조해보자.)
![](https://images.velog.io/images/heewonkim-dev/post/5c491f00-6b37-4dab-938d-4dde52f727aa/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-07-08%20%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB%2010.57.35.png)

* 각각의 컴포넌트는 각자 고유의 기능을 가지고 있고, UI의 한 부분을 담당한다. 
* 독립적인 컴포넌트들을 여러 개 만들고 한데 모아 복잡한 UI를 구성할 수도 있고, 더 나아가 복잡한 애플리케이션도 만들 수 있다.
* 원하는 수정사항에 맞추어 기존 컴포넌트의 위치만 수정해주면 되서 컴포넌트 개발은 많은 장점을 가지고 있다.


<br>
<br>
<br>


> Written with [StackEdit](https://stackedit.io/).

> Written with [StackEdit](https://stackedit.io/).
