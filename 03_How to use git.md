### 1. git을 활용하기 위한 순서

1. `mkdir`을 통한 폴더를 생성
2. `git init` 을 통한 관리자 폴더로의 전환
3. `touch` 를 통한 "파일"을 생성
4. `git add`를 통한 파일을 폴더에 인식
5. `git commit -m "파일명"` 으로 git내에 파일을 인식시켜 줌







### 1. `git` 의 `push`와 `pull`

___

- `git push origin master`: 파일을 올리는 것
- `touch` : 파일을 만드는 것
- `git log --oneline` : log를 한줄로 보여주는 것
- `git remote rename ----를 ---- 로` : 이름을 바꾸는 것
- `git clone` : 원격 저장소에서 다운로드 없이 코드를 복사 받는 것(처음에만)
- `git pull oringin master` : 원격 저장소에서 정보를 다운 받는 것 



<h3> 2`rm` 과 `rm -r`

___

- `rm` : 파일을 삭제
- `rm -r 폴더명` : 폴더를 지우는 것, 하위 폴더에 있는 .git 을 지운다.
- `cd ~` : 절대경로로 이동 가장 상위 폴더로 이동한다.
- `cd ~/폴더명` : 원하는 폴더로 이동이 가능하다
- `mv 이동할파일or폴더/이동할 장소` : 폴더나 파일을 이동할 수 있다.