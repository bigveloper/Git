# branch
 - `main`?? `master`?? 
 - 2020년 6월 Go 언어에서 인종차별적 요소나 주종관계를 담고 있는 whitelist / blacklist 와 master/slave 라는 용어를 프로젝트에서 제거하기로 결정하면서 업계 전반에 이런 부분을 제거 하는 움직임이 일어났다고 한다.(그런 의미가 아니라는 반대 의견도 당연히 있었다.) 이후 `master` 를 기본 branch 로 사용하던 git 에서도 이 논의가 이루어졌고 `branch` 사용자가 지정할 수 있도록 변경 하였다.
 - 결국 `main` = `master` 이라는 뜻이다. (검색하다 궁금해서 이 부분에 대해서 검색해 봄) 
 - github 도 `main` 을 선택했다고 한다. 
 - 그러나 project 에서 `branch` 의 이름을 꼭 `main` 이나 `master` 로 지정지 않을 수 있고, project 에 맞는 이름으로 지정해 줄 수도 있다.

## git bracn create
- 명령어 : `git branch branchName`
- 먼저 `status` 를 사용하여 git repository 내부 상황을 살펴본다.(branch 확인)
```
이름@이름ui-MacBookPro Git % git status         
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```
브런치가 main 으로 되어 있는것을 확인 했다. `Your branch is up to date with 'origin/main'.`  
그럼 명령어를 통해 branch 를 생성 해 준다.
`이름@이름ui-MacBookPro Git % git branch Git_1.0 main`

## repository 의 branch 확인
- 명령어 : 
`1. git branch`  
`2. git branch -v`
```
이름@이름ui-MacBookPro Git % git branch
  Git_1.0
* main
```
```
이름@이름ui-MacBookPro Git % git branch -v
  Git_1.0 d3d0f90 Update pull.md
* main    d3d0f90 Update pull.md
```
Git_1.0 이라는 branch 가 생성 된 것을 확인 할 수 있다.  
main(=master) branch 앞에 * 이 있다.  
현재는 main 으로 branch 가 지정되어 있다.  
그럼 이제 Git_1.0 branch 로 이동 해 보자  

## branch 이동 = checkout
- 명령어 :  
`1. git checkout branchName`  
`2. git checkout -b branchName`
```
이름@이름ui-MacBookPro Git % git checkout Git_1.0
Switched to branch 'Git_1.0'
```
branch 가 `Git_1.0` 로 바뀐것을 확인해 볼수 있다.  
명령어를 통해 확인 해 보자
```
이름@W이름ui-MacBookPro Git % git branch
* Git_1.0
  main
```
`Git_1.0` 의 앞에 * 이 있으므로 선택 되어 있는 것을 확인 할 수 있다.  
branch 를 생성하면서 바로 이동하는 명령어가 바로 `2. git checkout -b branchName` 이다.  
아래 내용에서 살펴보자
```
이름@이름ui-MacBookPro Git % git checkout -b Git_1.1
Switched to a new branch 'Git_1.1'

이름@이름ui-MacBookPro Git % git branch 
  Git_1.0
* Git_1.1
  main
```
`checkout -b` 를 사용하니 brach 가 생성 되면서 바로 생성된 brach 를 지정하는것을 확인 했다.  

## branch 삭제 하기
- 명령어 : git branch -d branchName
앞서 만들었던 `Git_1.0` branch 를 삭제 해 보자
```
이름@이름ui-MacBookPro Git % git branch -d Git_1.0
error: Cannot delete branch 'Git_1.0' checked out at '/Users/whyj/Documents/FrontEnd/Git'
```
error 라고?? 사용중이구나..
```
이름@이름ui-MacBookPro Git % git branch
* Git_1.0
  main

이름@이름ui-MacBookPro Git % git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
```
main branch 로 옮겨간 후에 확인
```
이름@이름ui-MacBookPro Git % git branch
  Git_1.0
* main
```
자 이제 삭제
```
이름@이름ui-MacBookPro Git % git branch -d Git_1.0
Deleted branch Git_1.0 (was d3d0f90).

이름@이름ui-MacBookPro Git % git branch
* main
```
`Git_1.0` 은 삭제 되었고 `main`만 남았다.

## 생성한 branch 를 원격 repository 에 push 하기
명령어 : git push --set-upstream origin branchName
원격 repository 로 보낼 때는 `push` 를 사용하니까 해보자
```
이름@이름ui-MacBookPro Git % git push             
fatal: The current branch Git_1.0 has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin Git_1.0
```
아.. 안돼.. `git push --set-upstream origin Git_1.0` 이렇게 작성 하라고 한다. 
- 현재 원격 repository 에는 main branch 밖에 없고, 다른 branch 가 바로 push 되면 에러가 발생되는 것이다. 그래서  --set-upstream 옵션을 주는 것이다.
```
이름@이름ui-MacBookPro Git % git push --set-upstream origin Git_1.0
Password for 'https://bigvieloper@github.com': 
remote: Invalid username or password.
fatal: Authentication failed for 'https://github.com/bigveloper/Git.git/'
whyj@WhyJui-MacBookPro Git % git push --set-upstream origin Git_1.0
Password for 'https://bigvieloper@github.com': 
Enumerating objects: 63, done.
Counting objects: 100% (63/63), done.
Delta compression using up to 8 threads
Compressing objects: 100% (49/49), done.
Writing objects: 100% (63/63), 17.72 KiB | 4.43 MiB/s, done.
Total 63 (delta 23), reused 5 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (23/23), done.
remote: 
remote: Create a pull request for 'Git_1.0' on GitHub by visiting:
remote:      https://github.com/bigveloper/Git/pull/new/Git_1.0
remote: 
To https://github.com/bigveloper/Git.git
 * [new branch]      Git_1.0 -> Git_1.0
Branch 'Git_1.0' set up to track remote branch 'Git_1.0' from 'origin'.
```
에러는 없군, 그럼 잘 생성되었나 확인해 본다.
```
이름@이름ui-MacBookPro Git % git branch -r
  origin/Git_1.0
  origin/HEAD -> origin/main
  origin/main
```
`git branch -r` 은 참고로 원격 repository 의 branch 를 확인하는 명령어 이다. local 에서는 그냥 `git branch` 를 사용 하듯 말이다.
내용을 보니 잘 생성 된 것으로 확인 된다.

## 마무리
- branch 를 생성, 이동, 삭제 까지 할 수 있다.

