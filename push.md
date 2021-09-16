# push
`commit`에서 해봤던 내용이다.
일단 `push` 는 `commit` 이 되어야 할 수 있다.

다시, `commit` 부터 해보자

```sh
Git % ls -al
total 168
drwxr-xr-x  21 name  staff   672 Sep 15 00:07 .
drwxr-xr-x  12 name  staff   384 Sep 14 00:52 ..
drwxr-xr-x  14 name  staff   448 Sep 15 00:12 .git
-rw-r--r--   1 name  staff  4830 Sep 13 21:54 Git.md
-rw-r--r--   1 name  staff     5 Sep 13 21:40 README.md
-rw-r--r--   1 name  staff  3660 Sep 14 22:13 add.md
-rw-r--r--   1 name  staff  5784 Sep 14 22:13 branch.md
-rw-r--r--   1 name  staff  1131 Sep 14 22:13 checkout.md
-rw-r--r--   1 name  staff  2952 Sep 14 22:13 clone.md
-rw-r--r--   1 name  staff  5621 Sep 14 22:13 commit.md
-rw-r--r--   1 name  staff  2762 Sep 15 00:07 fetch.md
-rw-r--r--   1 name  staff  1587 Sep 15 00:07 head.md
-rw-r--r--   1 name  staff  1331 Sep 15 00:07 merge.md
-rw-r--r--   1 name  staff     1 Sep 13 21:54 patch.md
-rw-r--r--   1 name  staff  2857 Sep 14 22:13 pull.md
-rw-r--r--   1 name  staff     8 Sep 13 21:54 push.md
-rw-r--r--   1 name  staff    14 Sep 13 21:54 repository.md
-rw-r--r--   1 name  staff    12 Sep 13 21:54 revision.md
-rw-r--r--   1 name  staff    16 Sep 13 21:54 staging Area.md
-rw-r--r--   1 name  staff   743 Sep 14 22:13 status.md
-rw-r--r--   1 name  staff     7 Sep 13 21:54 tag.md
```
여기다 `test.md` 파일을 만든 후 `push` 까지 할 것이다.
```sh
Git % ls -al
total 168
drwxr-xr-x  21 name  staff   672 Sep 15 00:07 .
drwxr-xr-x  12 name  staff   384 Sep 14 00:52 ..
drwxr-xr-x  14 name  staff   448 Sep 15 00:12 .git
-rw-r--r--   1 name  staff  4830 Sep 13 21:54 Git.md
-rw-r--r--   1 name  staff     5 Sep 13 21:40 README.md
-rw-r--r--   1 name  staff  3660 Sep 14 22:13 add.md
-rw-r--r--   1 name  staff  5784 Sep 14 22:13 branch.md
-rw-r--r--   1 name  staff  1131 Sep 14 22:13 checkout.md
-rw-r--r--   1 name  staff  2952 Sep 14 22:13 clone.md
-rw-r--r--   1 name  staff  5621 Sep 14 22:13 commit.md
-rw-r--r--   1 name  staff  2762 Sep 15 00:07 fetch.md
-rw-r--r--   1 name  staff  1587 Sep 15 00:07 head.md
-rw-r--r--   1 name  staff  1331 Sep 15 00:07 merge.md
-rw-r--r--   1 name  staff     1 Sep 13 21:54 patch.md
-rw-r--r--   1 name  staff  2857 Sep 14 22:13 pull.md
-rw-r--r--   1 name  staff     8 Sep 13 21:54 push.md
-rw-r--r--   1 name  staff    14 Sep 13 21:54 repository.md
-rw-r--r--   1 name  staff    12 Sep 13 21:54 revision.md
-rw-r--r--   1 name  staff    16 Sep 13 21:54 staging Area.md
-rw-r--r--   1 name  staff   743 Sep 14 22:13 status.md
-rw-r--r--   1 name  staff     7 Sep 13 21:54 tag.md

-rw-r--r--   1 name  staff     0 Sep 15 00:25 test.md
```
`test.md` 파일을 만들었다.
그럼 commit 전에 `add .` 를 해준다.
뭔가 변화가 있을때는 `status` 로 확인
```sh
Git % git add .
Git % git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   test.md
```
그럼 이제 `commit` 을 해줄 단계
```sh
Git % git commit -m "add test.md" 
[main c2a2139] add test.md
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test.md
```
`commit` 이 되었고, 이제야 드디어 `push` 를 해줄 차례
```sh
Git % git push origin main
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (5/5), 489 bytes | 489.00 KiB/s, done.
Total 5 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 1 local object.
To https://github.com/bigveloper/Git.git
   db1ab71..d8c5748  main -> main
```
사실 여기서 error 가 났었다. 이유는 내가 `원격 repository` 에서 작성 내용들을 `commit` 했고,
`local repository` 와 일치 가 된 뒤에 `commit` 을 했어야 했는데, 안되어서 error 가 발생되었었다.
여기서 하나 배운다. `commit` 전에 `pull` 받고 `commit` 하고 `push` 하자.
```sh
Git % git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```
### `push` 완료
