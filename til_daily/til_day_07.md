# Today I Learned [2021. 6. 22. Tue]

2021년 6월 22일 화요일의 배운 내용을 기록한 문서입니다.  
(스프린트 내용은 추후 따로 파일을 추가할 예정 입니다. 대신 Achievement Goal들과 요구사항들을 적어두었습니다 .🙂)


<br><br>



## Achievement Goals

-   스프린트에 작성된 HTML, CSS를 보며 복습할 수 있다.
-   HTML, CSS, JS로 두 숫자의 사칙연산을 할 수 있는 계산기를 만들 수 있다.
-   Github 웹 GUI를 이용해, Drag & Drop으로 과제를 제출할 수 있다.

<br><br>

## Bare Minimum Requirements

>Bare Minimum Requirements는 소프트웨어가 그 역할을 하기에 필요한 **최소한의 요구사항**입니다. 소프트웨어의 프로토타입을 빠르게 만들고, 프로토타입을 두고 기획자, 디자이너와 함께 회의를 하고 유져 경험을 개선할 수 있습니다. 개발자도 프로토타입을 생성하고 공유하고, 테스트하는 과정에서 이 소프트웨어에서 생길 수 있는 오류를 좀 더 빠르게 예측할 수 있습니다. 



**Step 1 - CSS 마음껏 수정하여 예쁜 계산기 만들기**

-   `calculate.html` 파일은 그대로 두고, `yourStyle.css` 파일을 수정합니다.
-   자신이 원하는 디자인으로 계산기를 꾸며보세요.

**Step 2 - 버튼이 잘 동작하는지 확인하기**

-   버튼을 클릭했을 때, 각 버튼이 잘 동작하는지 개발자 도구의 콘솔 탭에서 확인하세요.

**Step 3 - 기본적인 계산 기능 구현하기**

-   연산 시 `script.js`의 `calculate` 함수를 활용할 수 있도록 함수 `calculate`를 작성합니다.
-   처음 숫자 버튼을 클릭했을 때, 첫 번째 화면에 누른 숫자가 나타나야 합니다.
-   숫자 버튼과 연산자 버튼을 순서대로 클릭했을 때, 첫 번째 화면는 숫자, 두 번째 화면에는 연산자가 나타나야 합니다.
-   숫자 버튼, 연산자 버튼, 숫자 버튼을 순서대로 클릭했을 때, 화면에 숫자, 연산자, 순자가 순서대로 나타나야 합니다.
-   숫자 버튼, 연산자 버튼, 숫자 버튼, 엔터 버튼을 순서대로 클릭했을 때, 화면에 숫자, 연산자, 숫자, =, 연산 결과가 순서대로 나타나야 합니다.
-   AC 버튼을 클릭했을 때, 화면에 0, +, 0, =, 0 이 순서대로 나타나야 합니다.

**Step 4 - `SpecRunner.html`의 모든 테스트를 통과한 후 Github 홈페이지에 파일을 업로드 하여 과제 제출하기**

-   미리 작성된 `SpecRunner.html` 파일을 열고, Requirements을 전부 구현했는지 확인 합니다.
-   무작정 따라하고 과제 제출하기 영상을 참고해서 코드스테이츠 레포지토리로 과제를 제출합니다.

<br><br>


## Advanced Challenges

> Advanced Challenges는 여러분이 필수적으로 해야 하는 과제는 아닙니다. 앞서 Bare Minimum Requirements를 달성하고, 시간이 남거나 더 깊은 공부가 필요할 때 도전할 수 있는 과제입니다.

이번 Advanced Challenges는 실제 계산기처럼 display(화면)가 있고, 버튼을 클릭할 때마다 화면의 숫자가 변경되면서 동작합니다. 시중에 판매중인 계산기와 비슷하게 동작하도록 만듭니다.

**Step 1 - Advanced Challenges 테스트 활성화 시키기**

-   `spec/script.test.js`, `script.js`, `yourStyle.css` 파일의 주석을 제거하고, Advanced Challenges 테스트가 잘 작동하는지 `SpecRunner.html` 파일을 열고 확인합니다.
-   아래와 같이 `0` 하나만 보이는, 이전과 다른 계산기 모습이 보여야 합니다!

![image](https://s3.ap-northeast-2.amazonaws.com/urclass-images/OHeRLbBCg-1615200901506.png)

[그림] 계산기의 display에 0이 나타납니다.

  

**Step 2 - 숫자 버튼을 누르고 화면에 숫자를 입력하기**

-   숫자 버튼을 눌렀을 때, 계산기의 화면에 숫자가 보여야 합니다.
-   숫자 버튼을 여러 번 눌렀을 때, 계산기 화면에 숫자가 이어붙여져야(concatenation) 합니다.

**Step 3 - Enter 버튼을 눌러 계산하고, AC 버튼으로 초기화 시키기**

-   연산자 버튼을 눌렀을 때, 계산기 화면에 보이는 숫자를 따로 저장하고 계산할 준비해야 합니다.
-   Enter 버튼을 눌렀을 때, 이전에 저장한 숫자와 계산기 화면에 보이는 숫자를 계산한 결과를 화면에 보여줘야 합니다.
-   두 정수의 사칙연산을 수행하는 calculate 함수를 작성합니다.
-   AC 버튼을 누르면 초기 상태로 돌아갈 수 있어야 합니다.
-   미리 작성된 `SpecRunner.html` 파일을 열고, Requirements을 전부 구현했는지 테스트를 돌려서 확인 합니다.


<br><br>


> Written with [StackEdit](https://stackedit.io/).
