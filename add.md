# add
git add 파일명 은 해당 파일이 Staging Area 로 이동한다. (= index) 에 추가 
git add . 하면 현재 폴더의 전체 파일을 Staging Area 로 이동 시킨다.(add 한칸 띄고 . 이다.)  
commit 전의 단계, commit 하기 위해 먼저 필요한 폴더(SourceTree) 를 하나 (mkdir 폴더명) 사용하여 만들어 주었다.
```
이름@이름ui-MacBookPro FrontEnd_Basic % mkdir SourceTree
이름@이름ui-MacBookPro FrontEnd_Basic % ls -al
total 24
drwxr-xr-x   8 이름  staff   256 Sep 13 03:04 .
drwxr-xr-x   9 이름  staff   288 Sep 12 23:02 ..
-rw-r--r--@  1 이름  staff  6148 Sep 13 02:44 .DS_Store
drwxr-xr-x  13 이름  staff   416 Sep 13 02:59 .git
drwxr-xr-x   3 이름  staff    96 Sep 13 02:59 Git
-rw-r--r--   1 이름  staff    16 Sep 12 23:02 README.md
drwxr-xr-x   2 이름  staff    64 Sep 13 03:04 SourceTree
drwxr-xr-x   9 이름  staff   288 Sep 12 23:07 frontend_basic
```
여기서 git add SourceTree 도 해보고, git add . 도 해보고 해도 git status 로 확인 해 봤을 때 commit 해야 할 상태는 확인 되지 않았다.  
```
이름@이름ui-MacBookPro FrontEnd_Basic % git add SourceTree

이름@이름ui-MacBookPro FrontEnd_Basic % git status
On branch main
Your branch is behind 'origin/main' by 1 commit, and can be fast-forwarded.
  (use "git pull" to update your local branch)

nothing to commit, working tree clean

이름@이름ui-MacBookPro FrontEnd_Basic % git add .

이름@이름ui-MacBookPro FrontEnd_Basic % git status
On branch main
Your branch is behind 'origin/main' by 1 commit, and can be fast-forwarded.
  (use "git pull" to update your local branch)

nothing to commit, working tree clean
```
`pull` 받으라서 또 한번 받아줬다.
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
Updating 00fec87..f86f7a5
Fast-forward
 Git/Git.md | 14 ++++++++++++--
 1 file changed, 12 insertions(+), 2 deletions(-)
 
이름@이름ui-MacBookPro FrontEnd_Basic % git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```
그래서 그냥 commit -m 으로 commit 하면서 해당 내용도 같이 남겨주었다.
```
이름@이름ui-MacBookPro FrontEnd_Basic % git commit -m "Add SourceTree" 
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```
그리고 난 후 git log 를 통하여 commit log 를 확인 해 보았으나, SourceTree 가 commit 된 것은 확인 할 수 없었다.(Git.md `파일` commit 내용만 확인 가능)  
```
이름@이름ui-MacBookPro FrontEnd_Basic % git log

commit f86f7a5df6838d4fa81d874f2823662000c70d94 (HEAD -> main, origin/main, origin/HEAD)
Author: bigveloper <77265558+bigveloper@users.noreply.github.com>
Date:   Mon Sep 13 03:03:24 2021 +0900

    Update Git.md

commit 00fec878f9f1fa584df28f8cfee570538afe801f
Author: bigveloper <77265558+bigveloper@users.noreply.github.com>
Date:   Mon Sep 13 02:57:02 2021 +0900

```
그럼 `commit` 에 대한 개념을 알아보자.
