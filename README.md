# CodeSquadCodeReview

## 진행 방법
[CodeSquadCodeReview 저장소](https://github.com/HaeSeongPark/CodeSquadCodeReview)를 기반으로 코드리뷰 를 시작한다
- 시간 : 금요일 오후 2-3시 /  개인 당 10~15분
- 주제 : 자기단계 or 원하는 것!
- 준비할 것
- [개인] 요구사항, 접근방법, 코드에 의거하여 발표할 슬라이드를 만들어 목요일 저녁까지 올린다.
- [모두] 개인이 올린 슬라이들을 읽어 다음 날 다른 사람 발표에 대비한다.

# 코드 리뷰 준비 과정
> 저장소 브랜치에 자신의 github 아이디에 해당하는 브랜치가 존재해야 한다.
> 자신의 github 아이디에 해당하는 브랜치가 있는지 확인한다.

1. 자신의 github 아이디에 해당하는 브랜치가 없는 경우 브랜치 생성 요청 채널을 통해 브랜치 생성을 요청한다.
프로젝트를 자신의 계정으로 fork한다. 저장소 우측 상단의 fork 버튼을 활용한다.

2. fork한 프로젝트를 자신의 컴퓨터로 clone한다.
```
git clone https://github.com/{본인_아이디}/{저장소 아이디}
ex) https://github.com/HaeSeongPark/CodeSquadCodeReview
```

3. clone한 프로젝트 이동
```
cd {저장소 아이디}
ex) cd CodeSquadCodeReview
```

4. 본인 아이디로 브랜치를 만들기 위한 checkout
```
git checkout -t origin/본인_아이디
ex) git checkout -t origin/HaeSeongPark
```

5. commit
```
git status //확인
git rm 파일명 //삭제된 파일
git add 파일명(or * 모두) // 추가/변경 파일
git commit -m "메세지" // 커밋
```

6. 본인 원격 저장소에 올리기
```
git push --set-upstream origin 본인_아이디
ex) git push --set-upstream origin HaeSeongPark
```

8. pull request
	- pull request는 github 서비스에서 진행할 수 있다.
	- pull request는 original 저장소의 브랜치(자신의 github 아이디)와 앞 단계에서 생성한 브랜치 이름을 기준으로 한다.

	```
	ex) code-squad/swift-laddergame godrm 브랜치 기준 => godrm/swift-laddergame ladder-step1
	```
	
9. merge

10. 기본(upstream) 브랜치 전환 및 base 저장소 추가하기(최초 시작하기 단계 한번만 하면 됨)

	```
	git checkout 본인_아이디
	git remote add upstream base_저장소_url

	ex) git checkout HaeSeongPark
	ex) git remote add upstream https://github.com/HaeSeongPark/CodeSquadCodeReview.git
	```

	- 위와 같이 base 저장소 추가한 후 remote 브랜치 목록을 본다.

	```
	git remote -v
	```

11. 기본 base 저장소와 sync하기 (PR 보낸 내용을 자신의 기본 저장소와 합치기)

	```
  git checkout 본인_아이디
	git fetch upstream
	git rebase upstream/본인_아이디
	ex) git rebase upstream/godrm
	```
