# Linux TIL 02

2021년 6월 23일에 작성된 문서 2번 입니다.
linux 배운 내용을 정리했습니다.

### 절대 경로와 상대 경로

* 경로:
	*  명령어 **`pwd`**로 확인할 수 있는 **절대 경로**
		* **기준점**으로부터의 **절대적인 위치**
		* **기준점을 루트폴더(`/`)**
		* 특정 폴더나 파일이 루트폴더로부터 어떤 폴더로 진입하는 경우 만날 수 있는지
	* **현재 위치로부터 상대적인 위치**를 나타내는 **상대 경로**
		* **특정 폴더 또는 파일의 위치를 현재 위치를 기준점**으로 나타냄. 
		* **현재 위치**한 폴더는 **점**(`.`)
		* **상위 폴더**는 **두 개의 점**(`..`)



> macOS

**절대 경로 `/Users/[username]/helloWorld/hello/`**
* 루트폴더(`/`)에는 폴더 Users. 
* 폴더 Users로 진입하면, 폴더 [username] 확인. 
* 폴더 [username]에 진입하면, 폴더 helloWorld
* 폴더 helloWorld에 진입하면 폴더 hello를 발견. 


**현재 경로(`/Users/[username]/helloWorld/hello/`)**
*  `ls`로 확인되는 폴더나 파일은, 상대 경로로 `./`을 붙여 표현 가능. 
	* 현재 폴더 아래의 폴더 hi로 진입하려면, `cd`를 이용
		* **점(`.`): 현재 폴더**
		* **슬래시(/): 폴더 내부** 
		*  `./`는 "**현재 폴더 아래**의"라는 뜻
			*  `./hi`는 현재 폴더 아래의 폴더 hi
		*  `cd`와 함께 사용한다면, 현재 폴더 아래의 폴더 hi로 진입하라는 뜻

```
# '#' 기호는 설명을 위해 사용하였습니다.
cd ./hi # 현재 폴더 아래의 hi 폴더로 진입하는 명령
pwd

# (macOS) 
/Users/[username]/helloWorld/hello/hi

ls
# helloWorld.txt hiComputer.txt
// 점슬래쉬(./)는 현재 폴더
```

```
# '#' 기호는 설명을 위해 사용하였습니다.
mv helloWorld.txt ../../
ls
# hiComputer.txt
cd ../../
pwd
# (macOS) /Users/[username]/helloWorld/
ls
# hello helloWorld.txt hi.txt

// 현재 폴더 아래에 있는 파일 helloWorld.txt를 
// 폴더 helloWorld로 이동
// mv와 상대 경로를 이용해 helloWorld.txt파일을 
// 상위 폴더로 이동
```



---

### 관리자(root) 권한



* 절대 경로 기준점 루트폴더(`/`)는 Linux 관리자 영역. 
	* 사용자의 권한으로 폴더나 파일 생성, 변경, 삭제 불가

* Linux 관리자의 가장 큰 특징: 
	* 어떤 일이 있어도 일반 사용자에게 관리자 권한(루트 권한)을 완전히 안넘김
	* 해당 프로그램을 설치, 변경 또는 삭제할 수 있는 관리자 권한만 전달
		* 관리자 권한이 필요한 경우: 새 프로그램을 설치, 프로그램을 변경 또는 삭제하는 경우 
	* 사용자와 관리자를 명확히 분리하여 사용자의 실수로 발생할 수 있는 시스템 에러로부터 운영체제 보호

 
 
* 루트폴더로 이동하여 명령어 `mkdir`을 이용해 폴더 test를 생성: 
	* "Read-only file system" 이라는 에러
	* 읽기전용(**Read-only**)이라는 말은, **폴더나 파일을 생성, 변경 또는 삭제할 수 없다는 의미**



  
<br>

```
# '#' 기호는 설명을 위해 사용하였습니다.
whoami
# [username]
// 현재 로그인된 사용자를 확인하는 명령어 whoami
```



* **`whoami`로 확인할 수 있는 사용자**는, 폴더의 형태로 존재. 
	* 운영체제에 등록된 사용자를 확인하기위해, 하위 폴더macOS: `Users/`)로 이동. 
	* macOS 처음 설치할 때 입력했던 username이 폴더의 형태로 생성되어 있음. 

* 사용자 권한은 username 폴더 내에서만 자유롭게 사용
	* username에 맞게 폴더를 생성하여 해당 폴더 내에서 권한을 사용하도록 제한
* 관리자 권한을 이용하면, 다른 사용자 폴더에 영향. 
	* 당연히 시스템 자체에도 접근이 가능. 
	* 관리자 권한으로 변경한 내용은, 사용자 권한으로 해결 불가.

* 사용자 폴더의 경로(Path): `~/`로 표시. 
	* **물결기호(`~`): 루트폴더(`/`)로부터 사용자 폴더(username)까지의 경로를 축약한 형태.**


---
  

### sudo: 관리자 권한을 획득하는 명령어



```
# '#' 기호는 설명을 위해 사용하였습니다.
pwd
# (macOS) 
/Users/[username]/helloWorld/hello/
```




* `sudo`: **기본적 CLI 명령어의 앞에 작성**, **관리자 권한을 일시적으로 획득**하는 명령어입니다. 
* `sudo`는 **한시적으로 관리자 권한**을 가지기때문에 **항상 비밀번호와 함께** 사용. 


```
// 명령어 `mkdir`을 이용해 폴더 두 개를 생성

mkdir justMkdir
sudo mkdir sudoMkdir
password: 
# 타이핑을 해도 출력이 없습니다. 
비밀번호가 출력되지 않더라도, 
입력이 정상적으로 이뤄지고 있습니다.

ls
# hello justMkdir sudoMkdir helloWorld.txt hi.txt
```


*  `sudo`를 이용해 생성한 폴더의 소유자는 루트
	* 관리자 권한으로 생성되었다는 뜻
* `sudo`를 사용하지 않은 폴더 justMkdir은 사용자 소유의 폴더 
*  `ls -l`로 특정 폴더나 파일의 권한을 확인 가능


  <br><br>

----



### 텍스트 에디터 nano




```
nano hello.js  # hello.js 를 nano에서 엽니다.
nano # 그냥 실행할 수도 있습니다.
```


  

### nano 화면 살펴보기

텍스트 에디터 nano의 구성요소

![image](https://s3.ap-northeast-2.amazonaws.com/urclass-images/-eeGqE5Mi-1613728866459.png)


-   1. 파일 이름 안내
-   2. 파일 편집 화면, 실제로 여기서 텍스트 파일을 편집
-   3. 사용에 필요한 각종 단축키




  



<br><br><br>





> Written with [StackEdit](https://stackedit.io/).
