# fetch
`fetch` 는 간단하게 말하면 `pull` 을 절반만 실행 한 것 이다.  
다시 말하면 `pull = fetch + merge`, `fetch + merge = pull` 이다.  
  
    
`fetch` 와 같은 경우에는 `pull`이 있기 때문에 정확히 어떤기능에서 사용되는지 아직까지는 확인 해 볼 수 없었다. 
다만 바로 `pull` 을 받게 되면 `merge` 까지 이루어 지기 때문에, 그전에 확인 해 보기 위해서 사용하지 않을까 싶다.  
혹은, 내가 지정한 `branch` 에만 적용하고 싶을 때? 사용할 수도 있겠다.
 
명령어 : `git fetch origin main`
먼저는 원격 repository 에서 뭔가 변화를 주어야 `fetch` 또는 `pull` 할게 있겠다.
항상 `status` 를 통해 repository 의 상태를 먼저 살펴본다.
```
이름@이름ui-MacBookPro Git % git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```
음, 일단 `fetch` 해보자..
```
이름@이름ui-MacBookPro Git % git fetch origin main
remote: Enumerating objects: 8, done.
remote: Counting objects: 100% (8/8), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 6 (delta 3), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (6/6), 1.59 KiB | 232.00 KiB/s, done.
From https://github.com/bigveloper/Git
 * branch            main       -> FETCH_HEAD
   6852bb2..d411cf4  main       -> origin/main
```
뭔가 되긴 했다.  
여기서 보면, 새로운 `branch` 가 생겼고, 이름은 `FETCH_HEAD` 로 확인된다.  
그럼 `merge` 된 것이 아닌 어떠한 변화가 있는 파일들이 새로운 `branch` 에 반영 되었다.  
그럼 병합을 해볼텐데, `pull` 을 사용해도 되고, `merge` 를 사용해도 되는데, `merge` 를 사용해 보자.  
그전에 `status` 를 통해 상태를 확인 해 주고,  
```
이름@이름ui-MacBookPro Git % git status
On branch main
Your branch is behind 'origin/main' by 2 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

nothing to commit, working tree clean
```
  merge 명령ㅇ :
`git merge FETCH_HEAD`
```
name@nameui-MacBookPro Git % git merge FETCH_HEAD
Updating 6852bb2..d411cf4
Fast-forward
 fetch.md | 14 +++++++++++++-
 1 file changed, 13 insertions(+), 1 deletion(-)
```
 `pull` 이랑 같은 모습
 그럼 `status`  
```
name@nameui-MacBookPro Git % git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```
해보니 위에서는 `(use "git pull" to update your local branch)` 라며 `pull` 을 받으라 했지만,  
`merge` 하고 나니 사라졌다.

## 정리
- `fetch` 는 새롭게 commit 된 것들을 `merge` 이전의 상태로 FETCH_HEAD 라는 `branch` 로 반영한다.

