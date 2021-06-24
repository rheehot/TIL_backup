# Git TIL 01

2021년 6월 24일에 작성된 문서 1번 입니다.
Git 배운 내용을 정리했습니다.

---

### Git Intro (들어가기)
#### 버전 관리의 장점들
1. **버전 관리** : 각 버전 별 변경 이력들을 저장하는 작업
2. 이전 버전으로 되돌아가야 하는 상황이 발생할 경우 이전의 **변경 이력이 기록되어 있으니 되돌아가는 것이 가능** 
3. **변경 사항** 작성으로 누가 어떤 파일을 추가, 수정, 삭제했는 지 확인 가능.
4. Git으로 관리되는 파일은 Github, GitLab, Bitbucket 등의 여러 **원격 저장소를 이용해 백업과 협업** 가능

---
### Git

* 소스 코드 기록을 관리하고 추적할 수 있는 **‘분산형 버전 관리 시스템’** 
	* 개발자의 **코드를 효율적으로 관리**하기 위해 개발
* **스냅샷** : 특정 시점에 생성된 **백업 복사본** 
* **commit** : 하나 하나 **스냅샷을 만들어 주는** 작업 
	* commit으로 **변경 사항에 대한 스냅샷**이 만들어짐 
* 이전의 **기록들에 대한 추적**이 가능
* 소스 **코드가 변경된 이력** 확인 가능 
* 특정 시점에 저장된 **버전과 비교** 가능 
* 특정 시점으로 **되돌아가기**도 가능

---

### Github


* **Github : Git Repository를 관리할 수 있는 클라우드 기반 서비스** 
	* Git으로 버전을 관리하는 폴더에 대해 Github을 통해 여러 사람들이 공유하고 접근. 
* **Github에서 Code Review 등을 통해 협업** 가능

<br>

----
### Github 유용한 용어들
#### **기여(contribute)**: 

* **오픈 소스**(소스 코드가 공개된 소프트웨어)는 누구나 자유롭게 해당 **기능을 추가하고 개선** 가능. 
	* commit 기록으로 수정 사항을 확인할 수 있고 변경 코드도 볼 수 있다.

<br>

#### Git repository :

- 내가 작업하는 **소스 코드 폴더가 버전 관리**를 받게 하기 위해서는 내 폴더를 **Git의 관리 아래**에 둬야 함.  
- **Git repository** : **Git으로 관리되는 폴더**
  - Git repository 는 **Remote Repository와 Local Repository**를 제공. 
    - **작업**할 때는 **Local Repository**
    - 작업한 **코드를 공유**하려면 **Remote Repository**에 업로드. 

<br>

#### Fork :

*  **원격 저장소를 내 원격 저장소로** 가지고 오는 작업
	* 다른 사람이 Remote Repository에 올린 소스 코드를 내 Local Repository 로 가지고 올 수도 있다.

<br>

**Clone** : 

* 이 코드를 수정하기 위해서 **내 컴퓨터로 가져오는** 작업.
	* Fork 를 하고나면 나의 Remote Repository에 코드를 옮겨온 상태.  
	*  Remote Repository에 있는 코드를 Clone 해서 내 컴퓨터로 가지고 올 수 있다.

<br>

####  Push : 

* **변경 내용을 commit을 통해 저장**해 준 뒤, **Remote Repository에 반대로 올려주는** 작업
	*  Local Repository에 기록해 놓은 **commit을 Remote Repository로** 업로드. 

<br>

####  Pull request : 

* Push를 완료하고 나면 GitHub에 내가 제안한 코드 **변경사항에 대해 반영 여부를 요청.**
* Remote Repository에서 변경 사항이 있을 때 Local Repository 로 가져오는 Pull 작업도 가능


---
### Git 설치와 환경설정

>mac은 터미널을 열고 단순하게 `git`이라고 치면 설치 끝!

#### 사용자 정보

Git을 설치하면 가장 먼저, 사용자 이름과 이메일 주소를 설정하자.
 (이 때는 Github에 등록된 사용자 이름과 이메일 주소 사용)

```
$ git config --global user.name "나의 사용자 이름"
$ git config --global user.email "내 이메일 주소"
```

-   `--global` 옵션: 사용자 홈에 저장되므로 git을 설정할 때 처음 한 번만 입력해도 된다. (나중에 github의 사용자 이름이나 이메일을 변경한다면, 이 명령어를 다시 입력해야)
-   프로젝트마다 다른 사용자 이름과 이메일 주소를 사용하고 싶으면 `--global` 옵션을 빼고 명령을 실행하자.

<br>

#### 에디터

>Git에서 커밋 메시지를 기록할 때, 특히 merge commit 확인 메시지가 나올 때 텍스트 에디터가 열립니다. 

이 때는 기본값으로 텍스트 에디터 vi가 열리는데, 나는 계속 nano를 써야하기 때문에 에디터를 nano로 설정해 주었다.
```
$ git config --global core.editor nano
```
<br><br><br>

----
### 표로 한 눈에 보기

|이름|기능|
|:---|:---|
|`Fork`|원격 저장소를 내 원격 저장소로|
|`Clone`|내 컴퓨터로 가져오는|
|`Push`|변경 내용을 Remote Repository에 올림|
|`Pull request`|코드 변경사항에 대해 반영 여부 요청|




<br><br><br>



> Written with [StackEdit](https://stackedit.io/).
