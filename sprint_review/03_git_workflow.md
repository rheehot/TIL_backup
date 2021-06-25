
# Sprint 03_querySelector

2021년 6월 24일에 작성된 문서 입니다.
스프린트 내용을 정리했습니다. (계산기 내용보다 사정상 먼저 업로드했습니다.)


## Git Workflow (2인 이상)

1. 일단은 서로의 **Github에** Sprint(물론 스프린트 말고도 이런 저런 프로젝트 등등)를 **Fork해온다. 이 때는 fork 버튼만 누르면 끝!**
<br>

2. 이제 자신의 **로컬 레포지토리에 Clone**해온다.
	* **명령어 : `git clone <레포지토리 URL>`**
	* 이 때, URL은 `.git`으로 끝나야한다.
<br>

3. 페어의 **Github 저장소를 서로 연결**한다. 
	 * **명령어 : `git remote add pair <레포지토리 URL>`**
	* 이 때, URL은 `.git`으로 끝나야한다.
	* 그리고 `pair` 부분은 다름 이름해도 된다. 

<br>

4. 내가 코드를 **수정하고 commit** 해야 한다.

	* **명령어 : `git add <내용을 바꾼 파일 이름>`**
	* 그리고 **commit한 내용을 메시지로** 띄우자.
	* **명령어 : `git commit -m '쓰고 싶은 말'`**
	* `-m` 옵션 없이 쓰면 자동적인 내용의 메시지가 된다.

<br>

5. commit하고 **수정한 파일을 다시 내 Github 저장소에** 올린다.

	* **명령어 : `git push origin master(or other branch name)`**
	* 여기서 `origin` 부분은 다른 이름으로 해도 된다. 
	*  `master` 역시 다른 브랜치 이름으로 설정했다면 그 이름을 써주자.

<br>

6.  **페어가 수정한 파일을 내 로컬 저장소로** 끌고 온다.

    * **명령어 : `git pull pair master(or other branch name)`**
	* 여기서 `pair` 부분은 다른 이름으로 해도 된다. 
	*  `master` 역시 다른 브랜치 이름으로 설정했다면 그 이름을 써주자.


<br>

7. 페어가 코드를 **수정하고 commit** 해야 한다.

	* **명령어 : `git add <내용을 바꾼 파일 이름>`**
	* 그리고 **commit한 내용을 메시지로** 띄우자.
	* **명령어 : `git commit -m '쓰고 싶은 말'`**
	* `-m` 옵션 없이 쓰면 자동적인 내용의 메시지가 된다.


<br>

8. 페어가 commit하고 **수정한 파일을 다시 페어 자신의 Github 저장소에** 올린다.

	* **명령어 : `git push origin master(or other branch name)`**
	* 여기서 `origin` 부분은 다른 이름으로 해도 된다. 
	*  `master` 역시 다른 브랜치 이름으로 설정했다면 그 이름을 써주자.


<br>

9.  **페어가 수정한 파일을 내 로컬 저장소로** 끌고 온다.

    * **명령어 : `git pull pair master(or other branch name)`**
	* 여기서 `pair` 부분은 다른 이름으로 해도 된다. 
	*  `master` 역시 다른 브랜치 이름으로 설정했다면 그 이름을 써주자.

<br>

**위의 과정을 계속 반복해주면 된다.** 

사실 1번부터 9번까지 중간에 겹치는 부분도 상당히 있다. 

>처음에 손에 익지 않아서 좀 헤맸는데 계속 손에 익을때 까지 노력해야할 것 같다. 

<br>
<br>
<br>

> Written with [StackEdit](https://stackedit.io/).
