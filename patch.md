# patch
원격 repository 로 push 하는 권한은 대개 아무에게나 주지 않는다.  
프로젝트 팀원들에게만, 선별적으로 부여한다. 인증절차는 대개 원격 저장소의 SSH Key 를 등록하면서 이루어진다.  
이러한 방식은, 오픈소스 프로젝트에서는 사용할 수 없다.  
오픈소스 프로젝트 라 할지라도 개발자의 신분에 따라 권한을 나눈다.  
원격 repository 의 Main Stream 소스코드에 직접 push 할 수 있는 권한을 가진 개발자를 `Commitor` 라고 부른다.  
`Commitor` 아래에는 다수의 `Contributor`가 존재한다. 이들은 push 권한이 없고 모든것은 `Commitor` 가 결정한다.  
`Contributor` 와 같이 프로젝트에 기여하고 있지만, push 권한을 갖지 않는 특수한 상황에 유용하게 사용 가능한 것이 `patch` 이다.  
commit 을 하나의 patch 파일로 만들 수 있고, 이를 `Commitor`에게 전달하면 내용을 검토하고 Main Stream 소스코드를 반영 할 수 있다.  

- patch 만들기
  - 특정 commit ID 를 지정하여 만들 수 있다.
  `git format-patch {commit ID}`
  - HEAD 로 부터 시작하여, 몇개의 commit 을 patch 로 만들고자 한다면, commit ID 대신 이렇게 만들 수 있다.  
   `git format-patch -{patch를 생성할 commit 수}`
  - 예) HEAD 로 부터 3개의 commit 으로 부터 patch 생성  
    `git format-patch -3`
    
 
