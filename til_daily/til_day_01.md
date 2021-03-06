# Today I Learned [2021. 6. 14. Mon]

2021년 6월 14일 월요일의 배운 내용을 기록한 문서입니다.  
(참고: agora states 사용법 관련 내용은 생략했습니다 🙂)
<br>
  
## 페어프로그래밍

* **페어프로그래밍이란?**

  말 그대로, '짝꿍'과 함께 진행하는 코딩이다.  
  페어 프로그래밍으로 실무에서 필요한 협업을 연습한다.  
  커뮤니케이션 능력은 협업에서 필수 요소!
  
  **현업에서 함께 일하고 싶은 사람** : ==코딩만 잘 하는 사람이 아닌, 소통이 잘 되는 사람!==
<br>
<br>


* **페어프로그래밍을 하는 이유**

  페어 프로그래밍으로 **개발자의 커뮤니케이션을 연습**하고, 서로 주고받는 **피드백으로 장점과 단점을 파악하고 개선**할 수 있다.

  >실제, 2인 팀과 개인이 비슷한 규모의 프로젝트를 진행할 때, 페어 프로그래밍을 했던 2인 팀이 개인으로 작업한 팀보다 오류 수가 절반으로 감소했다.

  현업에서 개발자 말고도, 개발 이해도가 낮은 직무와 소통을 하는 일이 자주 있다. 이 때, 상대를 잘 이해시킬 수 있는 능력도 개발자가 갖추어야 하는 필수 역량이다.

  <br>
  <br>

  
* **페어프로그래밍 방법**    

  1.  **진행 전, 스스로 개념 정리 시간** 가지기.
  2.  일정에 맞춰, 페어에게 DM 연락 후, 줌 또는 구글 meet 링크 접속.
	  * 파트 나누기 : 
	  	* 네비게이터: 전체적인 방향을 제시
		* 드라이버: 네비게이터 방향에 따라 화면 공유해 코드 작성 

  3.  한 문제, 또는 정해진 시간 단위로 역할을 바꿔가며 과제 진행.
  4.  **모르는 내용은 관련 내용 충분히 찾기**, 근데도 해결책 찾기 어렵다! 그럼 아고라 스테이츠에 질문!

<br>
<br>


* **네비게이터? 드라이버?**    

	* 네비게이터:
		* 숲을 보는 역할
		* 문제 해결 위한 전체적 방향 제시
		* 드라이버에게 **코드를 직접 알려주기 보다, 질문을 계속 던져 드라이버가 답을 찾을 수 있도록** 돕는다.
		* 드라이버가 적는 코드 중 **실수(오타, syntax 에러 등)가 있으면 바로바로 피드백!**
    

	* 드라이버:
		* 나무를 보는 역할
		* 네비게이터와 함께 문제 해결 방향을 고민
		* 네비게이터가 제안하는 방향에 따라, 구체적인 문제 해결 방법 생각 후, 코드 작성
		* 이 때, **드라이버는 자신이 작성한 코드를 네비게이터에게 설명할 수 있어야한다.**
		* 네비게이터의 **의견에 동의하지 않더라도 자기 의견을 숨기거나 강하게 내세우기보다, 합의점을 찾을 수 있도록 네비게이터와 충분히 소통하자**.
    
    <br>
    <br>


* **소소한 페어 프로그래밍 TIP**    

  `1. 과제 시작 전, 페어와 충분히 논의를 하자.`
`2. 페어와 실력이 다르다고 실망하거나 낙심하지 말자.(특히 나!)`
`3. 문제가 풀리지 않는다면, 각자의 시간을 조금 가져보자.`
`4. 과제 시작 전에 ice breaking time을 가져보자. 서로 어색하니까.`
`5. 첫째도 협업, 둘째도 협업, 셋째도 협업!`
`6. 서로 예의를 지켜가며 하자. 안그러면 기분 상해서 감정의 골이 깊어진다.`
<br>
<br>


## 수도코드 (**pseudo code**) 작성 방법

> 오늘 배운 것 중, 여기가 제일 중요하다! 앞으로를 위한 피가 되고 살이 되기 때문에 두고 두고 봐두자. 잘 써먹어야 나중이 편해진다!

<br>

* **수도코드(pseudo code)란?**
  수도 코드(의사 코드)는 프로그래밍 언어로 ==코드를 작성하기 전, 무엇을 어떤 과정을 통해 만들지 사람의 언어로 먼저 작성하는 것==이다.

<br>
  간단하게 아래의 예시를 보자.
 
	  여기 네 개의 종이컵 중 하나에는 맛있는 사탕이 있습니다. 
	  맛있는 사탕을 먹기 위해서는 사탕이 나올 때까지 
	  종이컵을 하나씩 뒤집어 확인해야 합니다

네 개의 종이컵을 뒤집어, 맛있는 사탕을 찾는 과정을 수도코드로 작성한다면,

  `1. 종이컵의 개수만큼, 종이컵을 하나씩 뒤집는다.`
  `2. 뒤집은 종이컵에 사탕이 있다면,`
  `3. 먹는다.`

요렇게 나온다. 그렇다면 이 수도 코드를 바탕으로, 프로그래밍 언어로 코드를 작성해보면 아래와 같다. (코드 자체보다 의미에 집중하자.)

```
for(let cupNumber=1; cupNumber<=4; cupNumber++){  
// 4개의 컵을 하나씩 확인하면서
if  (candy)  {  // 만약 사탕이 있다면
eat();  // 먹는다
}
}
```

<br>
<br>


* **수도 코드를 왜 작성해야 할까?**

  >컴퓨터는 대강 생각하고 짠 코드는 이해하지 못한다. 이해보다는 에러 메시지를 띄운다. 즉, **작은 부분부터 계획과 순서를 작성하는 연습이 필요**하다. 이 연습(수도 코드 짜는 연습)을 반복하면, 정말 간단한 수준의 코드는 머릿속으로 정확히 정리된 채로 코드를 작성할 수 있고, 점점 그 범위를 넓힐 수 있다.

  귀찮다고 **수도 코드 작성하는 연습을 게을리한다면, 나중에 큰 규모의 코드를 작성할 때 개고생을 하게 된다.** (잊지 말자!)

  >페어와 함께 코드를 작성할 때, 코드를 짜기 전에 **"수도 코드부터 작성해 볼까요?"로** 접근해보길 권장합니다!

	위의 문구에 써있는대로 실천을 해보도록 하자!
	
<br>
<br>

## 질문하는 방법
>질문하는 방법에 대한 학습은 필수 사항입니다. **개발자는 새로운 것을 끊임없이 학습해야 하기 때문에, 모르는 것을 제대로 질문하는 법을 반드시 알아야** 합니다.

<br>

**1. 검색은 질문의 시작.**

검색은 좋은 질문의 시작점이다.
우리가 무언가 모르는 것이 있다면, 이미 많은 사람들이 같은 내용을 궁금해했고, 수많은 질문과 답변이 오고 갔다는 사실을 기억해야 한다.

* 두 가지의 Good News
`1. 99%(대부분)의 문제는 많은 사람들에 의해 이미 해결되었습니다.`
`2. 우리가 겪는 문제는 이미 어딘가 해결책이 쌓여 있다. 단지 검색 스킬이 부족하거나 질문하는 법이 잘못되어 해결책을 못 찾아내는 것 뿐.`

  즉, 검색에 적절히 시간을 쏟으면, 해결책은 반드시 얻어낼 수 있다.


<br>

**2.  문제 해결 방법 찾는 일에 개선이 없다면, 개발자로의 성장이 많이 더딜 수 있다.**
   
   그렇기에 스스로 문제를 해결하거나, 좋은 질문을 하는 능력을 갖추면 현업에서 더욱 빛을 발할 것이다.

<br>

**3. 질문 개선 노력 : 검색 키워드 찾기**

>키워드를 찾아내면 **더 나은 질문을 빠르게** 할 수 있고, 그 경험을 통해 **더 좋은 질문을 할 수 있는 실력을 갖출 수 있습니다**. **이 과정을 여러 번 반복하면, 여러분은 코드를 첨부하지 않고도 키워드를 포함한 질문을 통해 원하는 답변을 얻어낼 수 있는 경지에** 다다를 수 있습니다.

이를 위한 **3가지의 팁**이 아래에 있다.

`Tip 1 : 검색 포털은 '구글'을 이용!`
`Tip 2: 'how to'는 마법의 단어! 이 단어를 붙여서 검색을 시작해보자.`
`Tip 3. 영어 못한다고 두려워하지 말자`

<br>

**4. 질문하는 것 자체가 너무 어렵다.**

	JUST ASK! 일단 질문하세요. (아주 중요하다! 꼭 기억해두자.)

* 질문하는 것이 어려운 이유:

	1. 내가 현재 겪고 있는 문제의 상황을 설명하는 게 쉽지 않다.    
	2. 내가 무엇을 모르는지 모른다.

**이 두 가지의 문제에 해당한다면, 무엇을 모르는 지에 대한 질문부터 해야 한다.**
**지금 질문하지 않으면, 지금 겪는 문제 상황을 영원히 개선할 수 없다.**
이 세상에 바보 같은 질문은 없다. (하지만 정성을 들이지 않은 질문은 있다.) 

만약 정성을 들이지 않은 질문을 했고, 이를 **책망하는 답변을 받더라도 답변자를 미워하지 말자**. 오히려 **나의 성장을 진심으로 응원하는 마음에, 날카로운 답변을 단 경우가 많다.** **이를 받아들이고, 본인을 발전시키는 동력으로 삼는 자세로 임하자.** 질문을 정성스럽게 작성하는 방법을 모르겠다면, 그냥 무작정 질문을 하고 답변자에게 혼날 용기라도 반드시 가져야한다.

<br>

**5. 질문 할 때, 좋은 제목을 달자.**

좋은 질문의 첫 번째 조건은, 좋은 제목! (아래의 예시를 참조하도록 하자.)

 `array의 reduce 메서드 사용 시 accumulator 인자 작동이 이해되지 않습니다.`

-   제목만으로 어떤 답변을 기대할지 판단할 수 있다.
	- 바쁜 동료에게 물어본다 생각하고, 질문을 작성하자.
	- 길게 쓰면, 질문의 포인트를 잃어버리기 쉽다.

* 질문을 요약하는데 어렵다면, 먼저 글을 작성한 다음 나중에 제목을 쓰자.
	* 글 내용에 부합하는 명확한 제목을 작성하는 좋은 연습 방법이 된다.

<br>

**6. 코드를 붙이기 전, 현 상황을 먼저 설명하자.**


우리의 상황은 두 가지 정보로 전달할 수 있다.  
`1.  내가 문제 해결을 위해 시도한 흔적`
`2.  그 시도들로 인해 얻은 오답`
   
상황을 이해시키는 과정이 있으면, 답변자에게 내 의도를 전달할 수 있다. 답변자도 상황을 더 빠르게 파악하고, 키워드 또는 답변을 제공할 수 있다.

<br>

**7. 자신이 처한 문제의 충분한 정보를 제공하자.**

이 말은 **절대 전체 코드를 복사해서 붙여 넣으라는 말이 아니다.**
(코드 이미지 캡처를 올리라는 말은 더더욱 아니다. 이미지는 코드를 복사할 수 없기 때문에 재연이 매우 힘들다.)

그렇다면 어떤 방법이 있을까?

1. 코드를 삽입 시, code snippet을 활용하자. 
2. 온라인 기반 클라우드 에디터 이용. (but, 조금 높은 난이도의 기술이 필요)
	이슈가 있는 코드만 공유해야해서 당장은 적용하기 어려움.
```
1. https://codesandbox.io/
2. https://codepen.io/
3. http://jsbin.com/ 
4. http://sqlfiddle.com/
```
이는 나중에 더 성장한 다음에 써보도록 하자.

<br>

**8. 질문자로서 해야 할 마지막 임무**

누군가가 내 질문에 도움을 주었다면, 그 답변으로 인해 문제를 어떻게 해결했는지 서술하고, 진심으로 감사를 전하자. 이 질문의 기록은 질문자와 답변자, 나중에 이 질문을 검색해 볼 모든 사람에게 도움이 된다.

**답변을 받았다고 해서 그냥 넘어가면 안 됩니다.**

내 상황의 어떤 부분이 문제였고, 어떻게 해결했는지 간단한 기록을 마지막으로 남기자. 나와 이 질문을 검색해 볼 모두가 성장할 수 있는 소중한 기록이 된다.

>질문하는 것 자체가 개발의 한 부분입니다. 질문을 피할 수 없다면, 제대로 질문하는 연습을 꾸준히 해주세요.

<br>

**9. 질문 시작 tip**

1.  발생한 에러 메시지, **궁금한 것을 검색(구글링)**하자.
 2. 할 수 있는 것을 최대한 해 본 뒤, 가이드에 따라 Agora States를 이용.
 >Agora States를 통해 질문하고 답변하는 일은 스스로에게 매우 좋은 경험이 됩니다.
    
3. Agora States의 답변으로 문제를 해결하려해도 문제가 해결되지 않는 경우에는 1, 2번을 반복.

4.  답변으로 주어진 Keyword나 action item을 가지고 다시 1, 2번을 반복. "그게 뭔가요?" 라는 무책임한 질문은 되풀이하지 말자.
    <br>

* **주의사항**

	Agora States에 질문을 올렸다고, 답변을 받을 때까지 마냥 기다리면 안 됨!

>답변이 달릴 동안 계속해서 원하는 결과를 얻기 위해 레퍼런스를 검색하는 훈련을 하시길 권장합니다.


-   [구글 검색을 더 효과적으로 하는 20가지 Tips](https://www.lifehack.org/articles/technology/20-tips-use-google-search-efficiently.html)
    
-   [stackoverflow의 how to ask](https://stackoverflow.com/help/how-to-ask)
    

  
  
  <br>

**10. 질문 방법 예시**

**제목:** 
`	함수를 실행했을 때 undefined만 반환됩니다. 콘솔에 찍으면 답은 잘 나와요.`

**내용:**
```
-   운영 체제: 예) macOS
-   노드 버전(node -v): 예) v14.16.0
```
    

**현재 어떤 스프린트를 진행 중이고, 어떤 문제에 부딪혔나요?**
```
예) 문자열 코플릿 1번을 풀고 있습니다.

인자 2개(이름, 성)를 입력받아서 두 개의 문자열을 붙이되, 
중간에 띄어쓰기를 작성해야 합니다.
    
인자 2개가 문자열인지 확인한 다음 맞는다면, 
인자 1 + ' ' + 인자 2라고 작성했는데 계속 undefined가 나옵니다.
```
**안 되는 부분을 해결하기 위해서 구체적으로 어떤 노력을 했나요?**
```
예) 코드에 undefined가 아니면 반환하라고 조건을 더 붙였는데 똑같이 나옵니다.

디버깅을 하려고 console.log를 사용했는데, 값은 제대로 뜹니다.
-   console.log를 지우면 계속 undefined가 떠요.
    
에러 코드를 구글링 해 보니 undefined는 string이 아니라는 답변이 나옵니다.
제가 어디를 놓치고 있는 것일까요?
```
**에러 코드를 붙여넣기 해 주세요.**
```
AssertionError: expected 'undefined' to equal 'string'

at Context. (/submission/index.test.js:20:59)

-   at processImmediate (internal/timers.js:456:21) ...
 ```   
    
**어떠한 부분에서 이해가 안 되었나요?**
```
console.log로 값을 찍으면 원하는 값으로 나오는데,
console.log를 빼고 값을 반환하려고 하면 undefined가 나옵니다.
```
    
**에러가 출력된 곳에서, 이유라고 생각하는 부분을 열 줄 이내로 붙여넣기 해 주세요. (잘 모르겠으면 에러라고 생각하는 곳을 넣어주세요)**
    
```
function  getFullName(firstName, lastName)  {

if(typeof firstName !==  undefined  &&  typeof lastName !== 
 undefined)  {

firstName +  ' '  + lastName;

// console.log(firstName + ' ' + lastName) 얘는 잘 나와요

}
}
```

검색했던 링크가 있다면 첨부해 주세요.
```
https://stackoverflow.com/questions/51603051/
javascript-functions-return-undefined
```
----------

> Written with [StackEdit](https://stackedit.io/).

