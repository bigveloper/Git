# tag
git repository 의 소스 버전을 표시하기 위해서는 commit 메세지 또는 branch 로 해서 표시하기 보단 tag 로 깔끔하게 하는 것이 좋다.

## tag 는 두 종류가 있다.
1. Lightweight tag : 특정 commit을 가리키는 역할
2. Annotated tag : 만든 사람, 이메일, 날짜, 메세지 까지 저장 + GPG(GNU Privacy Guard) 로도 서명 가능하다.

## 1. Lightweight tag
`git tag TagName` 으로 붙일 수 있다.
```sh
Git % git tag v1.0

Git % git tag
v1.0

```  
  
## 2. Annotated tag
`-a` 옵션을 사용한다.
```sh
Git % git tag -a v1.0.1 -m"Release version 1.0.1"

Git % git tag
v1.0
v1.0.1

Git % git show v1.0.1
tag v1.0.1
Tagger: bigveloper <bigveloper@gmail.com>
Date:   Wed Sep 15 02:22:29 2021 +0900

Release version 1.0.1
// 이하 내용 생략
```
## 3. tag 삭제하기
```sh
Git % git tag -d v1.0.1
Deleted tag 'v1.0.1' (was d65918b)

Git % git tag
v1.0
```
## 4. tag 원격 repository 에 올리기
```sh
Git % git push origin v1.0
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/bigveloper/Git.git
 * [new tag]         v1.0 -> v1.0
```
## 5. 원격 repository 에 올린 tag 삭제하기
```sh
Git % git push origin :v1.0
To https://github.com/bigveloper/Git.git
 - [deleted]         v1.0
```


