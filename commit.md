# commit
`commit` 을 하기 위해서는 몇가지 과정이 필요하다.  
Git 의 repository 의 구조는 크게 세가지로 구성되어 있다.  
작업폴더(Working Directory) > 인덱스(Staging Area) > 저장소(Head-Repository)  
원격 repository 랑 연결 되어 있는 local repository 에 업데이트 된 파일이 있어야 한다.  
```
이름@이름ui-MacBookPro Git % ls -al
total 160
drwxr-xr-x  21 이름  staff   672 Sep 14 02:22 .
drwxr-xr-x  12 이름  staff   384 Sep 14 00:52 ..
drwxr-xr-x  14 이름  staff   448 Sep 14 02:15 .git
-rw-r--r--   1 이름  staff  4830 Sep 13 21:54 Git.md
-rw-r--r--   1 이름  staff     5 Sep 13 21:40 README.md
-rw-r--r--   1 이름  staff  3660 Sep 14 01:38 add.md
-rw-r--r--   1 이름  staff  5784 Sep 14 00:17 branch.md
-rw-r--r--   1 이름  staff  1131 Sep 14 01:38 checkout.md
-rw-r--r--   1 이름  staff  2952 Sep 14 01:38 clone.md
-rw-r--r--   1 이름  staff     9 Sep 14 01:38 commit.md
-rw-r--r--   1 이름  staff     9 Sep 13 21:54 fetch.md
-rw-r--r--   1 이름  staff     8 Sep 13 21:54 head.md
-rw-r--r--   1 이름  staff     9 Sep 13 21:54 merge.md
-rw-r--r--   1 이름  staff     1 Sep 13 21:54 patch.md
-rw-r--r--   1 이름  staff  2857 Sep 14 01:38 pull.md
-rw-r--r--   1 이름  staff     8 Sep 13 21:54 push.md
-rw-r--r--   1 이름  staff    14 Sep 13 21:54 repository.md
-rw-r--r--   1 이름  staff    12 Sep 13 21:54 revision.md
-rw-r--r--   1 이름  staff    16 Sep 13 21:54 staging Area.md
-rw-r--r--   1 이름  staff   743 Sep 14 01:38 status.md
-rw-r--r--   1 이름  staff     7 Sep 13 21:54 tag.md
```
작업폴더(Working Directory) 내부다. 여기에 null.md 파일을 추가해 주겠다.
```
이름@이름ui-MacBookPro Git % touch null.md
```
추가 해주고, 확인 해 본다.
```
이름@이름ui-MacBookPro Git % ls -al
total 160
drwxr-xr-x  22 이름  staff   704 Sep 14 02:23 .
drwxr-xr-x  12 이름  staff   384 Sep 14 00:52 ..
drwxr-xr-x  14 이름  staff   448 Sep 14 02:15 .git
-rw-r--r--   1 이름  staff  4830 Sep 13 21:54 Git.md
-rw-r--r--   1 이름  staff     5 Sep 13 21:40 README.md
-rw-r--r--   1 이름  staff  3660 Sep 14 01:38 add.md
-rw-r--r--   1 이름  staff  5784 Sep 14 00:17 branch.md
-rw-r--r--   1 이름  staff  1131 Sep 14 01:38 checkout.md
-rw-r--r--   1 이름  staff  2952 Sep 14 01:38 clone.md
-rw-r--r--   1 이름  staff     9 Sep 14 01:38 commit.md
-rw-r--r--   1 이름  staff     9 Sep 13 21:54 fetch.md
-rw-r--r--   1 이름  staff     8 Sep 13 21:54 head.md
-rw-r--r--   1 이름  staff     9 Sep 13 21:54 merge.md

-rw-r--r--   1 이름  staff     0 Sep 14 02:23 null.md

-rw-r--r--   1 이름  staff     1 Sep 13 21:54 patch.md
-rw-r--r--   1 이름  staff  2857 Sep 14 01:38 pull.md
-rw-r--r--   1 이름  staff     8 Sep 13 21:54 push.md
-rw-r--r--   1 이름  staff    14 Sep 13 21:54 repository.md
-rw-r--r--   1 이름  staff    12 Sep 13 21:54 revision.md
-rw-r--r--   1 이름  staff    16 Sep 13 21:54 staging Area.md
-rw-r--r--   1 이름  staff   743 Sep 14 01:38 status.md
-rw-r--r--   1 이름  staff     7 Sep 13 21:54 tag.md
```
없었던 null.md 파일이 생겼다. 이제 commit 을 바로 하는 것이 아니고 인덱스(Staging Area) 로 먼저 옮긴 후 진행해야 한다.
```
이름@이름ui-MacBookPro Git % git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	null.md

nothing added to commit but untracked files present (use "git add" to track)
```
`add`를 해야 commit 을 할 수 있다. 이 `add` 가 Staging Area 로 보내는 명령어 이다.  
이 부분은 add 에서 좀 더 자세히 다루고 지금은 `commit` 에 집중하자  
일단 add 를 해주었다.
```
이름@W이름ui-MacBookPro Git % git add .
```
`add` 를 해주고 `status`를 통해 상태를 확인 해 보았다.
```
이름@이름ui-MacBookPro Git % git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   null.md
```
이제 커밋 할 수 있다.
```
이름@이름ui-MacBookPro Git % git commit -m "update null.md"
[main 785f2e0] update null.md
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 null.md
```
`git commit -m "update null.md"` 라는 명령어 를 통해서 `commit` 되었다. 그러나 이게 끝은 아니다.  
원격 repository 로 `push`를 해줘야 한다. 그전에 다시 `status` 를 통해서 상태를 확인한다.
```
이름@이름ui-MacBookPro Git % git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```
여기서도 `git push` 를 사용하라고 이야기 한다. `push` 를 해야 `원격 repository` 로 파일이 업로드 된다.
```
이름@이름ui-MacBookPro Git % git push origin main
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 265 bytes | 265.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/bigveloper/Git.git
   cfb8a63..785f2e0  main -> main
```
`push` 에 대한 부분도 `push` 에서 조금더 자세히 이야기 하겠지만, 간단하게 local 에 생성된 파일을 원격 repository에 말그대로 밀어넣는 것이다.  
반대로, `pull` 은 원격 repository 에 commit 된 파일을 받아 오는 것이다.
