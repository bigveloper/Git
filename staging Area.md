# Staging Area
명령어 : `git add .` 또는 `git add fileName`
git 에는 Staging Area 가 있다. commit 되기 전에 반드시 거쳐야 만 하는 중간 단계이다.  
바로 commit 하면 되지 왜 꼭 add 를 통해 Staging Area 를 거치는가? 장점이 있기 때문이다.  
- 일부분만 커밋할 때
- 충돌을 해결할 때
- 커밋을 다시 할때
`commit --amend` 라는 명령어로 `commit --amend` 전의 파일을 고쳐서 `Staging` Area 에 `add` 하기만 하면된다.
