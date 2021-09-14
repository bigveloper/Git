# repository
이 내용은 다뤘던 내용이지만, 다시 한번 개념을 잡는다.  
repository 는 크게 두곳으로 나누어 볼 수 있다.  
- local repository  
- 원격 repository (github, gitlab 등등)  
원격은 원격에서 만들면 되고 local 로 clone 을 해주어도 된다.  
local 에서는 해당 폴더에 `git init` 이라는 명령어를 통해 `git repository` 를 만들 수 있다.  
```
name@nameui-MacBookPro ~ % cd Documents
name@nameui-MacBookPro Documents % cd FrontEnd
name@nameui-MacBookPro FrontEnd % mkdir FE
name@nameui-MacBookPro FrontEnd % ls -al
total 931096
drwxr-xr-x  13 name  staff        416 Sep 15 01:09 .
drwx------+  5 name  staff        160 Sep 12 03:50 ..
-rw-r--r--@  1 name  staff      10244 Sep 14 02:51 .DS_Store
drwxr-xr-x  12 name  staff        384 Sep 13 22:08 .git
drwxr-xr-x   2 name  staff         64 Sep 15 01:09 FE
drwxr-xr-x   8 name  staff        256 Sep 13 21:38 FrontEnd_Basic
drwxr-xr-x  22 name  staff        704 Sep 15 00:50 Git
drwxr-xr-x  12 name  staff        384 Sep 15 00:54 Javascript_Basic
drwxr-xr-x  10 name  staff        320 Sep 12 22:41 React
-rw-r--r--@  1 name  staff  476706822 Sep 12 03:26 React.zip
drwxr-xr-x   3 name  staff         96 Aug 29 22:33 Vue
drwxr-xr-x   4 name  staff        128 Sep 14 00:52 basic_react
drwxr-xr-x   4 name  staff        128 Sep 14 00:46 react_basic

name@nameui-MacBookPro FrontEnd % cd FE
name@nameui-MacBookPro FE % ls -al
total 0
drwxr-xr-x   2 whyj  staff   64 Sep 15 01:09 .
drwxr-xr-x  13 whyj  staff  416 Sep 15 01:09 ..

name@nameui-MacBookPro FE % git init
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint: 
hint: 	git config --global init.defaultBranch <name>
hint: 
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint: 
hint: 	git branch -m <name>
Initialized empty Git repository in /Users/whyj/Documents/FrontEnd/FE/.git/

name@nameui-MacBookPro FE % ls -al
total 0
drwxr-xr-x   3 whyj  staff   96 Sep 15 01:09 .
drwxr-xr-x  13 whyj  staff  416 Sep 15 01:09 ..
drwxr-xr-x   9 whyj  staff  288 Sep 15 01:09 .git
```
  repository 를 만들 directory 를 찾아간 후, 그 안에 `repository` 로 쓰일 `directory` 를 생성한 후 내부에 들어가 `git init` 이라는 명령어를 통해 `git repository` 로 만들었다.  
  확인 하는 방법은 폴더 내에 `.git` 이 존재한다면 제대로 생성된 것이 맞다.
