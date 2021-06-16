
# Today I Learned [2021. 6. 16. Wed]

2021년 6월 16일 수요일의 배운 내용을 기록한 문서입니다.  
(Javascript 내용은 파일에 따로 담아두었고 대신 Achievement Goal을 적어두었습니다 .🙂)


## 문자열 (String)
사실 문자열은 여기서 다 다루질 못한다. 왠만하면 구글링을 통해 검색을 해보거나 아니면 MDN문서를 보도록 하자!

### Achievement Goals

-   문자열의 속성과 메소드를 이용해 원하는 형태로 만들 수 있다.
    -   문자열의 `length`라는 속성을 활용해 길이를 확인할 수 있다. `str.length`
    -   문자열의 글자 하나하나에 접근할 수 있다. `str[1]`
    -   문자열을 합칠 수 있다. `word1 + " " + word2`
    -   문자열을 원하는 만큼만 선택할 수 있다. `str.slice(0, 3)` 또는 `str.substring(0, 3)`
    -   영문을 모두 대문자로 바꿀 수 있다. `str.toUpperCase()`
    -   영문을 모두 소문자로 바꿀 수 있다. `str.toLowerCase()`
    -   문자열 중 원하는 문자의 index를 찾을 수 있다 `str.indexOf('a')` 또는 `str.lastIndexOf('a')`
    -   문자열 중 원하는 문자가 포함되어 있는지 알 수 있다. `str.includes('a')`

<br>

---

### Advanced Challanges

-   띄어쓰기 `(" ")` 로 문자열을 구분하여 배열로 바꿀 수 있다. `str.split(" ")`
-   위의 배열의 요소 사이에 띄어쓰기 `(" ")` 넣어 다시 문자열로 바꿀 수 있다. `str.split(" ").join(" ")`

---

### Learn Yourself
- `trim`  
- 공백 문자 : 탭 문자(`\t`), Carrige return(`\r`) 및 return(`\n`)
- 정규 표현식 (advanced)
- `replace` (advanced)
- `match` (advanced)

<br><br>

> Written with [StackEdit](https://stackedit.io/).
