# pull
 - 원격 저장소(github) 의 `repository` 의 내용을 가져와서(fetch) local repository(working Directory) 에 합친다.(merge)
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
