# checkout
 - branch 에서 설명을 너무 열심히 하다보니 이미 해버렸다.  
 - 현재 `branch` 는 두개 생성 되어 있다. `branch` name 은  
   `main` 과 `Git_1.0`이다. 기본으로 `main` 이 지정되어 있다.   
   
     
     
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

