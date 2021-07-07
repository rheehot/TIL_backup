# JavaScript TIL 12

2021년 7월 7일에 작성된 문서입니다.
javascript 배운 내용을 정리했습니다.
<br><br>

## 값 수준의 추상화

추상화는 **복잡한 어떤 것을 압축해서 핵심만 추출한 상태로 만드는 것**

>컴퓨터를 구성하는 장치는 0과 1만 이해합니다. 크롬 개발자 도구의 콘솔(console) 탭에서 다음의 코드를 입력했을 때, 어떤 과정을 거쳐 10이 출력되는지 몰라도 10을 출력할 수 있습니다. 그런 복잡한 것들은 크롬의 자바스크립트 해석기(엔진)가 대신해 주기 때문입니다.

```jsx
function sum(num1, num2) {
  return num1 + num2;
}
const output = sum(3, 7);
console.log(output); // --> 10
// 개발자 도구의 콘솔에서 실행하면, 계산 결과를 출력
```

<br>
  
#### 추상화의 이점

**고민거리가 줄어들고, 그래서 문제의 해결이 더 쉬워진다.**
-   **추상화 = 생산성(productivity)의 향상**

한편 **프로그램을 작성할 때, 자주 반복해서 사용하는 로직은 별도의 함수로 작성**하기도한다. 이 역시 **추상화의 좋은 사례**다. 추상화의 관점에서 함수를 바라보면, **함수는 사고(thought) 또는 논리(logic)의 묶음**이다.


```jsx
// getAverage 함수는 number 타입을 요소로 갖는 배열을 입력받아, 
// 모든 요소의 평균값을 리턴

function getAverage(data) {
  let sum = 0;
  for (let i = 0; i < data.length; i++) {
    sum = sum + data[i];
  }
  return sum / data.length;
}

// number 타입을 요소로 갖는 배열을 인자로 전달하기만 하면, 
// 복잡한 로직은 신경 쓰지 않아도 평균값을 얻을 수 있다.

let output = getAverage([1, 2, 3]);
console.log(output); // --> 2

output = getAverage([4, 2, 3, 6, 5, 4]);
console.log(output); // --> 4

//getAverage 함수는 배열을 인자로 받아, 평균값을 리턴
```
  
* **함수를 통해 얻은 추상화를, 한 단계 더 높인 것이 고차 함수**다. 
	* `getAverage` 함수는 **값(배열)을 전달받아, 이 값을 가지고 복잡한 작업을 수행.** **(값 수준에서의 추상화)**

> 함수
	>  = **값을 전달받아 값을 리턴**한다 
		= **값에 대한 복잡한 로직은 감추어져** 있다 
		= **값 수준에서의 추상화**

<br><br>

-   **값 수준의 추상화: 단순히 값(value)을 전달받아 처리**
-   **사고의 추상화: 함수(사고의 묶음)를 전달받아 처리**

**고차 함수를 통해, 보다 높은 수준(higher order)에서 생각할 수 있다.**

>고차함수 
>= **함수를 전달받거나 함수를 리턴**한다 
>= **사고(함수)에 대한 복잡한 로직은 감추어져** 있다 
>= **사고 수준에서의 추상화**
>
>추상화의 수준이 높아지는 만큼, **생산성도 비약적으로 상승**합니다. 
>
<br><br>
## 사고 수준의 추상화

```jsx
const data = [
  {
    gender: 'male',
    age: 24,
  },
  {
    gender: 'male',
    age: 25,
  },
  {
    gender: 'female',
    age: 27,
  },
  {
    gender: 'female',
    age: 22,
  },
  {
    gender: 'male',
    age: 29,
  },
];
```


>위와 같이 주어진 데이터를 순차적으로 처리하려고 할 때, **모든 작업을 하나의 함수로 작성할 수 있습니다.** 예를 들어 **남성들의 평균 나이를 구한다고 할 때에는, 다음과 같이 함수를 작성할 수 있습니다.**

```jsx
// 남성들의 평균 나이를 구하는 하나의 함수 getAverageAgeOfMaleAtOnce

function getAverageAgeOfMaleAtOnce(data) {
  const onlyMales = data.filter(function (d) {
    // data.filter는 배열의 각 요소에 인자로 전달받은 함수를 적용하고,
    // 그 결과가 true인 요소만을 갖는 배열을 리턴.
    return d.gender === 'male';
  });

  const numOfMales = onlyMales.length;

  const onlyMaleAges = onlyMales.map(function (d) {
    // onlyMales.map는 배열의 각 요소에 인자로 전달받은 함수를 적용하고,
    // 각 결과를 요소로 갖는 배열을 리턴.
    return d.age;
  });

  const sumOfAges = onlyMaleAges.reduce(function (acc, cur) 
  {
    // onlyMaleAges.reduce는 배열의 각 요소에 
    // 인자로 전달받은 함수를 적용하고,
    // 각 결과를 두 번째 인자로 전달받은 초기값(0)에 누적한 결과를 리턴.
    return acc + cur;
  }, 0);

  return sumOfAges / numOfMales;
}
```

  


<br><br>

**추상화는 고차 함수를 통해, 보다 쉽게 달성할 수 있다.** 

>아래의 `compose` 함수는 입력받은 함수를 순서대로 결합하는 고차 함수입니다. 각각의 작업(filter, map, reduce)은 별도의 함수로 분리되어, `compose`의 인자로 전달되는 콜백 함수가 됩니다.

```jsx
// 입력된 함수를 순차적으로 실행하는 고차함수 compose

function getOnlyMales(data) {
  return data.filter(function (d) {
    return d.gender === 'male';
  });
}

function getOnlyAges(data) {
  return data.map(function (d) {
    return d.age;
  });
}

function getAverage(data) {
  const sum = data.reduce(function (acc, cur) {
    return acc + cur;
  }, 0);
  return sum / data.length;
}

function compose(...funcArgs) {
  // compose는 여러 개의 함수를 인자로 전달받아 함수를 리턴하는 고차 함수
  // compose가 리턴하는 함수(익명 함수)는 임의의 타입의 data를 입력받아,
  return function (data) {
   // funcArgs의 요소인 함수들을 차례대로 적용(apply)시킨 결과를 리턴
    let result = data;
    for (let i = 0; i < funcArgs.length; i++) {
      result = funcArgs[i](result);
    }
    return result;
  };
}

// compose를 통해 함수들이 순서대로 적용된다는 것이 직관적으로 나옴.
// 각각의 함수는 다른 목적을 위해 재사용(reuse) 될 수 있다.

const getAverageAgeOfMale = compose(
  getOnlyMales, // 배열을 입력받아 배열을 리턴하는 함수
  getOnlyAges, // 배열을 입력받아 배열을 리턴하는 함수
  getAverage // 배열을 입력받아 `number` 타입을 리턴하는 함수
);

const result = getAverageAgeOfMale(data);
console.log(result); // --> 26
```

  
<br><br><br>

> Written with [StackEdit](https://stackedit.io/).
