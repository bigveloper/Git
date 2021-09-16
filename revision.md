# revision
git object 를 가리킬 수 있는 표현식  
확인 할 수 있는 방법은  

```sh
Git % git log
commit 9b11039907125a8b9a5928e26ab03be70550c0c8 (HEAD -> main, origin/main, origin/HEAD)
Author: bigveloper <77265558+bigveloper@users.noreply.github.com>
Date:   Wed Sep 15 00:49:46 2021 +0900

    Update push.md
```
```sh
Git % git rev-parse HEAD
9b11039907125a8b9a5928e26ab03be70550c0c8

```
```sh
Git % git rev-parse --short HEAD
9b11039
```  
위에 보면 `9b11039` 이라는 공통된 글자를 찾을 수있다.  
`git log` 로 찾았을 때는 commit 옆 글자의 앞자리  
`git rev-parse`로 찾았을때도 마찬가지로 글자의 앞자리  

commit 된 내용의 주소라고 보면 되겠다.
