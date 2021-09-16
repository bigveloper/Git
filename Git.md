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
```sh
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
```sh
FrontEnd_Basic % ls -al
total 8
drwxr-xr-x   5 이름  staff  160 Sep 12 23:06 .
drwxr-xr-x   9 이름  staff  288 Sep 12 23:02 ..
drwxr-xr-x  12 이름  staff  384 Sep 13 01:53 .git
-rw-r--r--   1 이름  staff   16 Sep 12 23:02 README.md
drwxr-xr-x   9 이름  staff  288 Sep 12 23:07 frontend_basic
```
여기서 .git 이 설치가 확인되면 git의 repository 역할을 할 수 있다. 검색을 할땐 ls 뿐만 아니라 -al 을 붙여줘야 숨겨진 파일들도 볼 수 있다.(for Mac)  
여기까지 왔다면, git 을 사용할 준비가 완료 되었다.

- 참고  
- https://linked2ev.github.io/devlog/2018/08/27/Git-1.-What-is-Git/
