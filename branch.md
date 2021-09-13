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
1. git branch 
2. git branch -v
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

## branch 이동
- 명령어 : git checkout branchName
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
