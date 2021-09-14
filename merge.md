# merge
`merge` 는 `병합` 을 뜻한다.
`fetch` 에서 사용 해 보았지만 다시 한번 설명 한다.
`pull` 을 받게 되면 기본적으로 `merge` 도 실행 된다.
내가 작업한 내용을 원격 repository 에 `push` 하려 할때, 나의 local repository 의 최신버젼이 아닐경우  
(내가 pull을 받고 작업하는 동안 다른 사람이 push 를 해버린 경우) 거부 된다. 이런경우 merge 를 해준다.  
만약, merge 하지 않은 상태로 이력을 덮어쓰게 되면 다른 사람이 push 한 업데이트 내역이 사라져 버린다.  

