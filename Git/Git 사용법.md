# Git 사용법

* [명령어](#명령어)
* [사용법](#사용법)
* [Branch 사용법](#branch-사용법)
* [원격저장소](#원격저장소)

---------------------

### 명령어

* **git init** : 파일에 .git을 만들어서 깃을 버전 관리 할 수 있다. 깃 저장소를 초기화 하고 추가적인 명령어를 사용할 수 있다.
* **git config** : 최초의 깃을 설정할 때 사용한다. 
* **git status** : 저장소에서 상태를 체크할 수 있다. 저장소 안에 어떤 파일이 있는지, 커밋이 필요한 변경사항이 있는지, 어떤 브랜치에서 작업 하고 있는지 등 확인할 수 있다.

* **git [branch](#branch-사용법)** : 새로운 브랜치를 만들고, 본인의 변경사항과 파일 추가 등의 타임라인을 만든다. 동료들과 함께 작업하고 본인의 변경사항을 원할 때 사용한다.
* **git add** : 깃이 새 파일들일 지켜보게 한다(새 파일을 추가하진 않는다.). 파일을 추가하면, 깃의 저장소 "스냅샵"에 포함된다.
* **git commit** : 가장 중요한 명령어이다. 변경사항을 만든 후 저장소의 "스냅샵"을 찍기 위해 입력한다.
* **git checkout** : 브랜치 이동이 가능하게 해준다.
* **git merge** : 브랜치 작업을 끝내고, 모든 협업자가 볼 수 있는 master브랜치로 병합한다.
* **git push** : 원격 저장소로 데이터를 보낸다.
* **git pull** : 로컬 컴퓨터에서 작업할 때, 작업하고 있는 저장소의 최신 버전을 원하면, 이 명령어로 부터 변경사항을 다운로드 한다. 다른 컴퓨터에서 내가 작업하던 작업물을 어디서든 사용이 가능하게 해준다.
* **git remote** : 현재 원격 저장소가 만들어져 있는지 확인이 가능하다.

------------------

### 사용법

* **git remote add origin https://github.com/본인 아이디/깃에 있는 Repositories 입력** (ex : test.git)
  * 만약 **faral: remote origin already exists.** 가 뜨면 **git remote rm origin** 을 입력하면 된다.
* 위의 명령어를 치면 origin에 올라가 있는 상태이다. But, github.com 에는 정보가 안올라 가 있다.
* **git push -u origin master** 입력하면 깃에 데이터가 올라간다.
* 깃에서 데이터를 받을려면 **git clone https://github.com/아이디/받을려고 하는 Repositories** 입력하면 된다.
* 전 버전 불러오기 **git reset 버전주소 --hard (공유전 내 컴퓨터에 있을 때에만 reset 작업)**
* git add (파일명) 대신에 **git commit -a** 로 하면 자동으로 **commit** 해준다.
* vim 까지 안키고 버전명을 바꿀 때 **git commit -am "바꿀 버전명"** 을 입력해 주면 된다.
* 만약 commit에서 버전명을 바꿔야 할 경우 **git commit --amend** 명령어를 쓰면 다시 바꿀 수 있다.

--------

### branch 사용법

* 브랜치 확인 : **git branch**
* 브랜치 생성 : **git branch 이름**
* 브랜치 이동 : **git checkout 이름**
* 브랜치 삭제 : **git branch -d 삭제할 브랜치 명**
* 로그에 모든 브랜치를 표시하고(gir log --branches), 그래프로 표현하고(graph), 브랜치 명을 표시하고(decorate), 한줄로 표시(oneline)
  * **git log --branches --graph --decorate --online**
* 병함 A 브랜치로 B 브랜치를 병합할 때 **(A <- B)**
  * **git checkout A, git merge B**
* master를 exp로 가지고 오고 싶으면 **git merge master**
* 병합중 충돌이 일어났을 때, git status를 하면 충돌이 일어난 파일 확인 가능! 충돌이 일어난 파일을 수정하면 된다.
* 만약 현재 작성중인 코드를 완료 못하고 다른 브랜치로 이동해야 할 때, **stash** 활용
* 특정 브랜치를 바로 로컬로 clone 하기 위해서는 **git clone -b <branch><remote_repo>** 를 사용한다.
  * (ex) **git clone -b hanium_ccj https://github.com/allsser/codingtogether.git**

-----------

### 원격저장소

* **git remote -v** : 만약 origin이 있으면 origin 안에 있는 주소가 무엇인지 확인이 가능하다.
* 저장소는 origin(기본) 뿐만이 아니라 이름을 할당하면 여러개가 가능하다.
* 만약 **fatal: remote origin already exists.** 가 뜨면 **git remote rm origin** 을 입력하면 된다. 다르게 지우는 방법은 **git remote remove 저장소 이름** 을 치면 삭제 된다.
* **git push -u master** : 이 명령어는 처음 한번만 해주면 나중에 git push만 해도 origin에 저장되어 있는 주소로 push한다.
* **git clone https://..........git .(현재 디렉토리에 다운).........git "새로운 디렉토리 이름"** : 새로운 디렉토리에 생성 및 파일 생성
* 아무것도 없이 **git clone https://.....git** 이면 원격 저장소의 디렉토리도 같이 생성
* git clone 을 통해 local 저장소로 받으면 자동으로 원격 저장소와 연결이 되어있다. git remote -v 로 주소 확인 가능

