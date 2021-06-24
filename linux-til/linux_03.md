﻿# Linux TIL 03

2021년 6월 23일에 작성된 문서 3번 입니다.
linux 배운 내용을 정리했습니다.


## 패키지와 패키지 매니저


* 패키지 안에 들어 있는 파일의 구성
	-   프로그램 파일
	-   프로그램 설치 파일
	-   프로그램 설치 설명서
	-   프로그램에 대한 정보를 담은 파일

* **패키지** : **프로그램이 정상적으로 설치되고 동작하기 위한 모든 파일이 압축**되어 있다. 
	* 프로그램에 대한 정보를 담은 파일
		* 프로그램 A를 설치하기 위해 프로그램 B가 필요하다는 정보도 함께 있다. 
		* 패키지를 이용해 프로그램을 설치하면, 패키지에 포함된 정보를 이용해 프로그램 B를 먼저 설치하고 나서 프로그램 A를 설치.


* **패키지 매니저**: 패키지의 설치, 변경, 삭제 등 **관리를 편하게 해주는 도구.** 
	* 모든 패키지의 저장소 위치를 저장하고 있다. 
	* 사용자가 패키지 매니저에게 특정 프로그램의 설치를 요청하면, 패키지 매니저는 **패키지가 저장된 위치에서 패키지를 다운로드 받아 설치 프로그램을 실행**. 
	* 설치된 모든 **프로그램의 업데이트를 확인**하거나, **필요없는 프로그램을 제거**하는 데에도 사용.


---

   ### MacOS  Homebrew 패키지 매니저 명령어 모음
   
   |명령어|기능|
   |:---|:---|
 |  `brew update`| 패키지의 업데이트 여부 확인|
   | `brew outdated`|업데이트 필요한 파일 조회|
   | `brew upgrade`| 프로그램 업그레이드|
   |  `brew info`| 프로그램의 정보 확인|
   | `brew install`| 프로그램 설치|
   | `brew list`| 설치된 프로그램 목록 보기|
   | `brew uninstall`| 프로그램 삭제|


<br><br>

> Written with [StackEdit](https://stackedit.io/).