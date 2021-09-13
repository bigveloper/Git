# clone
 - 명령어 : `git clone https://github.com/계정이름/저장소이름.git`
 - `git clone https://github.com/bigveloper/react_basic.git`  

`clone` 을 사용하기 위해서는 먼저 원격 repository 가 있어야 한다.  
  
```
이름@이름ui-MacBookPro FrontEnd % git clone https://github.com/bigveloper/react_basic.git
Cloning into 'react_basic'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
이름@이름ui-MacBookPro FrontEnd % cd react_basic
이름@이름ui-MacBookPro react_basic % ls -al
total 8
drwxr-xr-x   4 이름  staff  128 Sep 14 00:46 .
drwxr-xr-x  11 이름  staff  352 Sep 14 00:46 ..
drwxr-xr-x  12 이름  staff  384 Sep 14 00:46 .git
-rw-r--r--   1 이름  staff   13 Sep 14 00:46 README.md
```
FrontEnd 디렉토리(폴더)에 원격 repository 중 하나인 react_basic 을 `clone` 명령어로 다운 받아 왔다.  
내부 파일들 확인 해보니 `.git` 도 있는걸 보아 `git` 기능을 사용할 수 있다. 결국 commit, pull, push 등 가능하다.  
또 한가지,
`git clone https://github.com/bigveloper/react_basic.git basic_react`  
이런식으로 끝에 디렉토리(폴더) 이름을 정해준다면 정해진 이름으로 생성 한다.
```
이름@이름ui-MacBookPro FrontEnd % git clone https://github.com/bigveloper/react_basic.git basic_react
Cloning into 'basic_react'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
이름@이름ui-MacBookPro FrontEnd % ls -al
total 931096
drwxr-xr-x  12 이름  staff        384 Sep 14 00:52 .
drwx------+  5 이름  staff        160 Sep 12 03:50 ..
-rw-r--r--@  1 이름  staff      10244 Sep 13 21:33 .DS_Store
drwxr-xr-x  12 이름  staff        384 Sep 13 22:08 .git
drwxr-xr-x   8 이름  staff        256 Sep 13 21:38 FrontEnd_Basic
drwxr-xr-x  20 이름  staff        640 Sep 14 00:17 Git
drwxr-xr-x  10 이름  staff        320 Sep 10 23:02 Javascript_Basic
drwxr-xr-x  10 이름  staff        320 Sep 12 22:41 React
-rw-r--r--@  1 이름  staff  476706822 Sep 12 03:26 React.zip
drwxr-xr-x   3 이름  staff         96 Aug 29 22:33 Vue
drwxr-xr-x   4 이름  staff        128 Sep 14 00:52 basic_react
drwxr-xr-x   4 이름  staff        128 Sep 14 00:46 react_basic
이름@이름ui-MacBookPro FrontEnd % cd basic_react
이름@이름ui-MacBookPro basic_react % ls -al
total 8
drwxr-xr-x   4 이름  staff  128 Sep 14 00:52 .
drwxr-xr-x  12 이름  staff  384 Sep 14 00:52 ..
drwxr-xr-x  12 이름  staff  384 Sep 14 00:52 .git
-rw-r--r--   1 이름  staff   13 Sep 14 00:52 README.md
```
basic_react 가 생성 된 것을 확인 해 볼 수 있다.  
basic_react 디렉토리(폴더) 안에도 당연히 `.git` 파일이 있다. `git` 기능을 사용 할 수 있다.
