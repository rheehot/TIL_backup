# Git TIL 02

2021년 6월 24일에 작성된 문서 2번 입니다.
Git 배운 내용을 정리했습니다.

----
## Git Workflow (혼자) 

1. Remote에 있는 다른 Repository에서 **Fork**로 내 Repository에 가지고 오기 
	* 이 때는 그냥 fork 버튼만 누르면 된다.

<br>  

2. 내 컴퓨터에서 작업을 하기 위해서 **clone**. 
	* 이 때 **명령어는 `git clone <레파지토리 주소>`**

<br>

3. 내 컴퓨터의 **작업 공간(work space) 에서 작업에 들어간 파일들을 git의 관리 하에 있는 상태로 올려줄 수** 있다. (이 영역을 **staging area**) 
	* staging area에 들어오지 않은 파일: **unstaged** 혹은 untracked file
	* staging area에 있는 파일: **staged** 
	* 	**파일들이 어떤 스테이지에 있는지 알려주는 명령어는 `git status`**
		* **unstaged 상태 파일에 쓸 수 있는 명령어**
			* **`add`** : 파일을 **commit 할 수 있는 상태로** , staging area에 unstaged 상태인 파일을 추가
				* **`git add 파일 이름`**
			* **`restore`** : **commit되지 않은 Local Repository의 변경사항을 폐기**(discard changes)			
				* **`git restore 파일 이름`**


<br>

4. **staging area**에 들어온 파일들은 **commit이 가능**. 
	* commit 한 뒤, **내 remote repository에 push 해서 commit 기록을 remote 에도 남겨줄 수 있다**. 
		* 이 때 쓰는 명령어는 `git commit -m '쓰고 싶은 메시지'`

<br>

5. push 후, remote의 원래 레파지토리에 **pull request를 보내면 Remote Repository로 내가 수정한 코드를 업로드**할 수 있다.
	* Pull Request를 날리기 위해 **현재 Local Repository에 저장되어 있는 commit 기록들을 내 Remote Repository 에 업로드**해 줘야 함. 
	*  이 때는 `git push origin branch` 명령어를 사용. 
	*  git push origin main, git push pair dev 등 `git push` **뒤에 따라오는 명령어는 상황에 따라 변경** 가능.

<br>
6. 내가 남긴 commit들을 확인하고 싶을 때는, `git log` 사용. 터미널 종료는 q를 눌러 종료시킨다.


---
### 그 외의 상황

*  commit한 기록을 취소하고 에러를 수정하고 싶은 경우
	* `reset` 명령어를 통해서 **commit 을 취소** 가능
(**단, Remote Repository에 업로드 되지 않고 Local Repository에만 commit 해 놓은 기록**)
	* `git reset HEAD`

	* git reset 를 했을 때 터미널 창에는 변화가 없다. 
	* `git reset HEAD^` 로 가장 최신의 commit 을 취소할 수 있다. 
	* `HEAD`는 연속된 `^` 의 shortcut. 
		* `HEAD3` = `HEAD^^^` 

<br><br>

### 표로 대략적인 정리

|이름|명령어|기능|
|:---|:---|:---|
|fork|`fork 버튼`|다른 Repository에서 내 Repository에 |
|clone|`git clone <레파지토리 주소>`|내 컴퓨터에서 작업하려고|
|git status|`git status`|파일들이 어떤 스테이지에 있는지|
|add|`git add 파일 이름`|파일 **commit 할 수 있는 상태** , staging area에 unstaged 상태인 파일을 추가|
|restore|`git restore 파일 이름`|**commit되지 않은 Local Repository의 변경사항 폐기**|
|commit message|`git commit -m '쓰고 싶은 메시지`|commit 기록을 남기기|
|git push |`git push origin branch`|현재 Local Repository에 저장되어 있는 commit 기록들을 내 Remote Repository 에 업로드|
|commit check|`git log`|내가 남긴 commit들을 확인|
|reset|`git reset HEAD`|commit한 기록을 취소하고 에러를 수정|
|최신 commit reset|`git reset HEAD^`|가장 최신의 commit 을 취소|


---

### Git의 3가지 영역 및 상태

* git의 Local Repository 영역들
	* **Untracked area**는 Git이 관리하고 있지 않은 영역. 
	* **Tracked area**에 들어온 파일만 Git 관리를 받을 수 있다.

* **Tracked area** 내부 세 가지 상태
**Unmodified, Modified, Staged** 
	* **Unmodified** : 기존 **Commit한 파일을 수정하지 않은** 상태.
	* **Modified** : 기존 **Commit한 파일을 수정한** 상태.
	* **Staged** : **commit이 가능**한 상태. 

* **수정 파일을 commit 하기 위해서 staged area에 add 작업 필요.**
	* **Changes to be committed** : **staged** 상태의 파일 
	* **Changeds not staged for commit** : **Modified** 상태의 파일 
	* add 명령어를 통해 tracked area에 들어간 파일을 수정하게 되면 다시 modified 상태가 되기 때문에 다시 add하는 작업을 통해 파일을 staged 해 주는 작업이 필요.

<br><br><br>


## Git Workflow (2인 이상)

 1. 내 컴퓨터에서 **생성한 디렉토리를 `init` 명령어를 통해 Git의 관리 하에 들어가게** 만든다. 
	 * 내 컴퓨터에서 만든 디렉토리를 **Git의 관리 하에 들어가게** 만들어 주는 명령어는 **`git init`** 
	 * 기존 프로젝트를 **Git Repository로 변환하거나 새로운 Repository 초기화에 사용**. (Local Repository가 생성)

<br>

 2. 내 컴퓨터의 **Git 디렉토리를 Remote Repository와 연결**
	  * 변환한 **Local Repository를 Github에서 원격 관리** 위해서 **Local Repository를 Remote Repository와 연결**하는 작업이 필요. 
	  * 이 때 **`git remote add`** 명령어를 사용.

<br>

3. **다른 사람(또는 페어)의 Repository 와 연결**. Remote Repository를 연결함으로서 Github Repository를 함께 공유
	* 아까와 같이 `remote add`를 활용
	*  이번에는 **origin이 아닌 다른 이름과 연결하고자 하는 상대방의 Repository 주소를 입력**. 

* 잘 연결된 것이 맞는지 확인하려면 **`git remote -v` 명령어로 통해 현재의 Local Repository와 연결된 모든 Remote Repository 목록을 확인**

4.  pair 변경 사항, 내 **변경 사항을 Remote Repository를 통해서 공유**

5. `git pull` pair master 명령어로 **페어의 Remote Repository에 있는 작업 내용을 받아올 수 있다**. 받아오는 **내용은 자동으로 병합(merge)** 됨.
	* 만약 **충돌한 경우에는 `git status` 명령어를 통해 어떤 파일이 충돌하고 있는지** 확인.
	* 충돌이 일어난 부분은 하나 하나 직접 확인 후 수정이 필요.
		*  `Accept Current Change`를 클릭해 **내가 수정한 내용으로 파일에 반영.** 
		* `Accept Incoming Change`를 클릭해서 R**emote Repository의 내용으로 파일에 반영**. 
		* `Accept Both Changes`는 변경 사항 모두를 반영.
		* **수정을 마치면 병합 커밋(merge commit)을 생성해 주기 위해서 파일을 staging area로 추가.**
			* **Merge commit은 자동 Commit 메시지가 생성.** 
			* **Remote Repository에 Push하면 Merge branch ‘master’ of 라는 commit 메시지**가 기록.


<br><br><br>

> Written with [StackEdit](https://stackedit.io/).
