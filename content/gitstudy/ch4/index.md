---
title: "4장 : 깃허브로 백업하기"
date: 2019-11-29T17:38:30+09:00
weight: 5
---

### 1. 원격 저장소와 깃허브
- 원격 저장소
    - 지역 저장소가 아닌 컴퓨터나 서버에 만든 저장소를 말한다.
    - 지역 저장소와 연결되어 있으면서 '백업'과 '협업'이라는 중요한 역할을 한다.
- 깃허브로 할 수 있는 일
    - 원격 저장소에서 깃을 사용할 수 있다.
    - 지역 저장소를 백업할 수 있다.
    - 헙업 프로젝트에 사용할 수 있다.
    - 자신의 개발 이력을 남길 수 있다.
    - 다른 사람의 소스를 살펴볼 수 있고, 오픈 소스에 참여할 수 있다.

### 2. 깃허브 시작하기
- [깃허브](https://www.github.com)에 접속한 뒤 계정을 생성한다.
- 무료 계정과 유료 계정의 차이 : 협업할 수 있는 계정의 수가 제한되어 있다.
- 깃허브에 원격 저장소 만들기
    - repository를 새로 만들어 원격 저장소를 추가할 수 있다.
    - Add a License : 오픈 소스 프로젝트를 위한 저장소를 만들 경우 해당 오픈 소스의 라이센스를 선택한다.

### 3. 지역 저장소를 원격 저장소와 연결하기
- 지역 저장소를 만든다.
    - `git init [지역 저장소 이름]`
- 지역 저장소와 원격 저장소를 연결한다.
    - `git remote add [원격 저장소 이름] [원격 저장소 URL]`
    - 원격 저장소 이름 : 사용자 지정
    - github에서 지정되어 있는 URL :: `clone or download`를 눌렀을 때 나오는 URL
- 지역 저장소와 원격 저장소의 연결 확인
    - `git remote -v`

### 4. 원격 저장소에 올리기 및 내려받기
- 원격 저장소에 파일 올리기 :: `git push`
    - `git push origin master`
        - push : 원격 저장소에 올리겠다.
        - origin : 원격 저장소의 이름
        - master : 원격 저장소에 올릴 브랜치
- 원격 저장소에서 파일 받기 :: `git pull`
    - `git pull origin master`
        - pull : 원격 저장소에서 받아오겠다.
        - origin : 원격 저장소의 이름
        - master : 원격 저장소에 받아올 브랜치이름, 지역 저장소의 브랜치 이름


### 5. 깃 허브에 SSH 원격 접속하기
- 생략하도록 하겠다...
- 필요시 업데이트 하겠다...