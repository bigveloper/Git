# Git
## git 이란?
 - 형상 관리 도구(Configuration Management Tool)
 - 형상 관리 란? : 변경사항을 체계적으로 추적, 통제 하는 것(파일이 변경되었을 경우 변경된 내역을 기록하였다가 나중에 이를 찾아 봐야 할 경우, 변경 원인과 변경 사항을 확인 할 경우에 대한 관리)
### git 의 특징
 - source code 를 주고받을 필요 없이 같은 파일을 여려명이 동시 작업하는 등 `병렬 개발` 이 가능 하고, 버전 관리가 비교적 쉬워 생산성이 증가 한다.
 - 소스코드의 수정 내용이 'commit' 단위로 관리되고, `patch` 형식으로 배포 할 수 있기 때문에 프로그램의 변동 과정을 체계적으로 관리 할 수 있고, 언제든지 지난 시점의 소스코드로 점프(checkout) 할 수 있다.
 - 새로운 기능을 추가하는 Experimental version (실험 버전) 을 개발할 경우, `branch` 를 통해 충분히 실험을 한 뒤 원래 프로그램에 합치는`merge` 방식으로 개발을 진행 할 수 도 있다.
 - `git` 은 `분산` 버전 관리를 하기 때문에, 인터넷이 연결되지 않은 곳에서도 개발을 진행 할 수 있으며, 중앙의 저장소가 문제가 생겨도 각 개발자들이 source 를 가지고 있어 원상복구 할 수 있다.
 - Team Project 가 아닌 personal Project 라도 git 을 통해 버전 관리를 하면 체계적인 개발이 가능 해 지고, 프로그램이나 patch 를 배포하는 과정도 간단해 진다.(pull 을 통한 update, patch파일 배포)
 ### git 의 장점
 - 속도(빠름)
 - 분산 버전 관리 시스템
 - 모든 작업자가 원본을 가지고 있다.
 - Loacl 에서 대부분의 작업을 할 수 있다.
 - branches/tags/master, 기타 revision 이동시 굉장히 빠르다.
 ### git 사용법
  - git 은 OS 가 window 라면 cmd 에서 mac 이라면 terminal 에서 git 명령어를 통해 사용한다. 그러나 git 명령어나 git 의 구조가 이해가 되지 않는다면 git GUI tool 을 사용해 비교적 쉽게 git 을 다룰 수 있다.
  - git 명령어 라면 cmd 나 terminal 이나 크게 차이 없고, GUI 를 사용한다면 더욱 크게 차이는 없다.
  - git 을 사용하려면 저장할 저장소가 필요하다. 그게 대표적으로는 한번쯤 들어봤을 github 이다. git과 github는 다른것
    - git 이 커피라면 github 는 커피숍(노마드코더)
  - git 의 구조를 먼저 이해하기 위해서 git GUI 중 하나인 sourceTree 를 사용하고, git 명령어도 직접 그리고 저장소는 github 를 사용해 연습했다.
  
## git 사용의 시작
 ### 시작
 - 먼저는 git 을 설치한다. git 을 검색하면 나온다.
 - github 의 계정을 만들고 로그인 하여, `repository` 를 만들어 준다.
 - `git config --global user.name "bigveloper"` 계정명은 아무이름이나 주어도 되지만, github 이름을 주는 것이 기억하기 좋겠다.
 - `git config --global user.eamil "bigveloper@gmail.com"` 이메일도 github 에 등록된 이메일 주소를 입력해 준다.
 - `git config --list`라고 검색해 보면
```
credential.helper=osxkeychain
core.excludesfile=/Users/이름/.gitignore_global
difftool.sourcetree.cmd=opendiff "$LOCAL" "$REMOTE"
difftool.sourcetree.path=
mergetool.sourcetree.cmd=/Applications/Sourcetree.app/Contents/Resources/opendiff-w.sh "$LOCAL" "$REMOTE" -ancestor "$BASE" -merge "$MERGED"
mergetool.sourcetree.trustexitcode=true
user.name=bigveloper
user.email=bigveloper@gmail.com
commit.template=/Users/이름/.stCommitMsg
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
core.ignorecase=true
core.precomposeunicode=true
```
라는 결과가 나오는데, 내가 입력했던 user.name 과 user.email 을 확인, sourcetree 를 사용하고 있는 것도 확인 해 볼 수 있다.  

 - 원하는 곳에 폴더를 만든다. `cd 폴더명` 으로 이동하여 그곳에 `mkdir 폴더명` 으로 폴더를 생성한다.
 - 폴더 안에서 git 명령어인 `git init` 을 입력하면 그곳이 git 저장소`repository` 가 된다.
```
이름@이름ui-MacBookPro FrontEnd_Basic % ls -al
total 8
drwxr-xr-x   5 이름  staff  160 Sep 12 23:06 .
drwxr-xr-x   9 이름  staff  288 Sep 12 23:02 ..
drwxr-xr-x  12 이름  staff  384 Sep 13 01:53 .git
-rw-r--r--   1 이름  staff   16 Sep 12 23:02 README.md
drwxr-xr-x   9 이름  staff  288 Sep 12 23:07 frontend_basic
```
여기서 .git 이 설치가 확인되면 git의 repository 역할을 할 수 있다. 검색을 할땐 ls 뿐만 아니라 -al 을 붙여줘야 숨겨진 파일들도 볼 수 있다.(for Mac)  
여기까지 왔다면, git 을 사용할 준비가 완료 되었다.

## status
 - git status 를 입력하면
 ```
이름@이름ui-MacBookPro FrontEnd_Basic % git status
On branch main
Your branch is behind 'origin/main' by 5 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

nothing to commit, working tree clean

이름@이름ui-MacBookPro FrontEnd_Basic % git status
On branch main
Your branch is behind 'origin/main' by 7 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

nothing to commit, working tree clean
```
이런 내용들이 나온다. 내가 계속 글을 작성하고, 수정할 때마다 원격저장소인 github 에 commit 된게 있다고 `pull` 받으라고 알려준다. 즉, 파일의 상태를 확인해 볼 수 있다.  

## pull
 - 원격 저장소(github) 의 `repository` 의 내용을 가져와서(fetch) local repository(working Directory) 에 합친다.(mergy)
 - git pull 명령어를 사용하여 받는다.
 ```
이름@이름ui-MacBookPro FrontEnd_Basic % git pull  
hint: Pulling without specifying how to reconcile divergent branches is
hint: discouraged. You can squelch this message by running one of the following
hint: commands sometime before your next pull:
hint: 
hint:   git config pull.rebase false  # merge (the default strategy)
hint:   git config pull.rebase true   # rebase
hint:   git config pull.ff only       # fast-forward only
hint: 
hint: You can replace "git config" with "git config --global" to set a default
hint: preference for all repositories. You can also pass --rebase, --no-rebase,
hint: or --ff-only on the command line to override the configured default per
hint: invocation.
Updating 4214dc9..22a01ef
Fast-forward
 Git/Git.md | 95 ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 95 insertions(+)
 create mode 100644 Git/Git.md
```
위에서 pull 받으라길래 받았다.  
원격저장소(github) 의 Git 이란 폴더의 Git.md 파일이 다운 받아졌다. 실제로 폴더에 가보자  
```
이름@이름ui-MacBookPro FrontEnd_Basic % ls -al  
total 24
drwxr-xr-x   7 whyj  staff   224 Sep 13 02:39 .
drwxr-xr-x   9 whyj  staff   288 Sep 12 23:02 ..
-rw-r--r--@  1 whyj  staff  6148 Sep 13 02:44 .DS_Store
drwxr-xr-x  13 whyj  staff   416 Sep 13 02:39 .git
drwxr-xr-x   3 whyj  staff    96 Sep 13 02:39 Git
-rw-r--r--   1 whyj  staff    16 Sep 12 23:02 README.md
drwxr-xr-x   9 whyj  staff   288 Sep 12 23:07 frontend_basic
```
위에서 ls -al 로 검색했을 때 없었던 Git 이라는 폴더가 생겼고, 확인해 보면 그안에 Git.md 라는 파일이 생성 되었다.
```
이름@이름ui-MacBookPro FrontEnd_Basic % cd Git
이름@W이름ui-MacBookPro Git % ls -al
total 16
drwxr-xr-x  3 whyj  staff    96 Sep 13 02:39 .
drwxr-xr-x  7 whyj  staff   224 Sep 13 02:39 ..
-rw-r--r--  1 whyj  staff  5639 Sep 13 02:39 Git.md
```
`pull` 받으래서 받았으니 이제 위와 같이 `pull` 받으라는 상태를 보여주진 않겠다.
```
이름@W이름ui-MacBookPro FrontEnd_Basic % git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```
역시 nothing to commit 이라고 한다.  
그러나, `Git.md` 는 지금 내가 작성하고 있는 파일이다. 원격저장소(github) 에서 `commit` 될 때 마다 `pull` 받으라고 할 것이다.  
확인해 보자
```
이름@이름ui-MacBookPro FrontEnd_Basic % git status
On branch main
Your branch is behind 'origin/main' by 5 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

nothing to commit, working tree clean
```
역시 그러했다.  

## commit

## push

## fetch

## merge
  
## patch

## checkout

## revision

## tag

## repository

## clone

## branch
 - `main`?? `master`?? 
 - 2020년 6월 Go 언어에서 인종차별적 요소나 주종관계를 담고 있는 whitelist / blacklist 와 master/slave 라는 용어를 프로젝트에서 제거하기로 결정하면서 업계 전반에 이런 부분을 제거 하는 움직임이 일어났다고 한다.(그런 의미가 아니라는 반대 의견도 당연히 있었다.) 이후 `master` 를 기본 branch 로 사용하던 git 에서도 이 논의가 이루어졌고 `branch` 사용자가 지정할 수 있도록 변경 하였다.
 - 결국 `main` = `master` 이라는 뜻이다. (검색하다 궁금해서 이 부분에 대해서 검색해 봄) 
 - github 도 `main` 을 선택했다고 한다. 
 - 그러나 project 에서 `branch` 의 이름을 꼭 `main` 이나 `master` 로 지정지 않을 수 있고, project 에 맞는 이름으로 지정해 줄 수도 있다.
 
## head



## staging Area



- 참고  
- https://linked2ev.github.io/devlog/2018/08/27/Git-1.-What-is-Git/
