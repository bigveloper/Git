# HEAD
- HEAD 는 현재 `checkout`된 commit 을 가리킨다.
- HEAD 는 항상 working directory 의 가장 최근 `commit`을 가리킨다.
- working directory 의 변화를 주는 git 명령어 들은 HEAD 를 변경하는 것으로 시작한다.
  
  local repository 로 간 후에 `git branch` 라는 명령어로 `HEAD` 로 가리킬 `branch` 를 확인한다.  
```sh
~ % cd Documents
Documents % cd FrontEnd
FrontEnd % cd Git
Git % git branch
  Git_1.0
* main
```
`git log` 라는 명령어로 살펴 보면, 
```sh
Git % git log
commit d411cf4fd7432e600b14712c59a3f87616dd42a1 (HEAD -> main, origin/main, origin/HEAD)
```
`(HEAD -> main, origin/main, origin/HEAD)` HEAD 가 main 을 가리키고 있다.  
그럼 `checkout` 을 통해서 Git_1.0 라는 이름을 가진 `branch` 로 변경 해 보겠다.
```sh
Git % git checkout Git_1.0
Switched to branch 'Git_1.0'
Your branch is up to date with 'origin/Git_1.0'.
```
이동 되었다.  
그럼 다시 살펴본다.
```sh
Git % git branch
* Git_1.0
  main
```
```sh
Git % git log   
commit d3d0f90445f9b0a4ce3397d2abead6f43ff39d15 (HEAD -> Git_1.0, origin/Git_1.0)
```
`HEAD` 가 `Git_1.0` 이라는 `branch` 를 가리키고 있다.  

## 정리
- 일단 이렇게 `HEAD` 가 어떻게 `branch` 를 가리키는 지 확인 해보았다.
- `HEAD` 는 최근 작업한 `commit` 을 혹은 작업한(하는) `branch` 를 가리킨다.
