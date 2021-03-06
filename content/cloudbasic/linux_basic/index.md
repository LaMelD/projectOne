---
title: "Linux Basic"
date: 2020-01-13T10:31:27+09:00
weight: 4
---

### 200116 Thurday ~ 200116 Thursday

---

## 1. Linux(리눅스)

- 리눅스란?
    - 컴퓨터 운영체제의 한 종류
    - 윈도우와는 다르게 오픈 소스 운영체제
    - 소스코드가 공개되어 있기 때문에 다양한 리눅스 기반의 운영체제가 존재
        - 구글의 안드로이드도 리눅스를 기반으로 만든 운영체제

- 운영체제란?
    - 사용자와 시스템 사이에서 편리한 인터페이스를 제공
    - 시스템의 각종 네트워크 장치 또는 하드웨어를 관리 및 제어
    - 운영체제의 종류로는 Windows, Mac OS, 리눅스, 유닉스, 안드로이드, IOS 등이 있다.

- 특징
    - 높은 이식성과 확장(C언어 기반)
    - 안정성과 신뢰성
        - 국제적이고 개방적으로 개발되었기 때문에 문제점에 대한 대처가 빠름
    - 계층적 파일 시스템
        - 최상위 디렉토리가 존재하고 모든 것들은 해당 디렉토리 하부에 존재
    
- 리눅스 기본 환경
    - 기본 구성 요소
        - 이미지 삽입 .. linux_default.png

    - 프롬프트
        - 현재 작업 디렉토리, 현재 로그인한 사용자 등에 대한 정보를 표시
        ex) \[root@localhost tester\]# cd ..

    - 명령줄 인터페이스
        - 텍스트 터미널을 통해 사용자와 컴퓨터가 상호작용하는 방식을 뜻한다.
        - 즉 작업 명령은 사용자가 컴퓨터 키보드 등을 통해 문자열의 형태로 입력하며 컴퓨터로부터의 출력 역시 문자열의 형태로 주어진다.
        - 명령어의 구조
            - 명령어 : 시스템에서 특정 작업을 하기 위해 실행하는 실행파일, 프로그램
            - 옵션 : 명령어를 어떻게 실행할 것인지 지정
            - argument : 명령어에 의해서 영향을 받는 파일 또는 디렉토리 등 특정 대상

## 2. 리눅스 명령어

- 디렉토리 작업
    - 현재 작업 디렉토리 : pwd
    - 디렉토리 이동 : cd \[이동 경로(절대/상대)\]
    - 디렉토리 내용 확인 : ls, ll
        - 옵션
            - -l : 출력 결과를 자세하게 출력
            - -a : 숨겨진 파일도 출력
            - -d : Argue로 특정 디렉토리를 입력할 때 해당 디렉토리 자체의 정보를 조회
            - -R : 하위 디렉토리 목록까지 출력
            - -F : 파일의 종류를 표시, 디렉토리 뒤에 /를 붙임
    - 디렉토리 생성 : mkdir \[이동경로\]
    - 디렉토리 제거 : mrdir \[디렉토리 이름\]

- 파일 작업
    - 파일 내용 확인
        - cat : 파일 내용 전체 출력
        - head : 파일 내용 중에서 위에서 몇 줄 출력
        - tail : 파일 내용 중에서 밑에서 몇 줄 출력
        - more : 파일 내용을 화면에 맞게 출력
        - 옵션 -f : 파일의 내용을 실시간으로 계속해서 조회
    - 생성 : touch \[v파일 이름\] : 빈 파일 생성

- 디렉토리 및 파일 작업
    - 복사 : cp \[옵션\] \[원본\] \[사본\]
        - -r : recursive, 폴더를 복사할 때
    - 이동 및 이름 변경 : mv
    - 제거 : rm -rf \[제거 대상\]
        - -rf : recursive, forced

- vi 편집기
    - 편집기 모드
        - Command mode
        - Edit mode
        - Last Line mode
        - 모드 전환: Edit <-(a, i, o / ESC)-> Command <-(ESC, ENTER / :, /)-> Last Line

    - Command mode 사용
        - 커서 이동
            - G : 마지막 줄로 이동
            - gg : 첫번째 줄로 이동
            - \[n\]G : n번째 줄로 이동
            - $ : 현재 줄의 맨 끝으로 이동
            - 0 : 현재 줄의 맨 앞으로 이동
            - w : 커서가 한 단어씩 오른쪽으로 이동
            - d : 커서가 한 단어씩 왼쪽으로 이동
        - 삭제
            - x : 한 문자 삭제
            - dd : 커서가 위치한 한 줄을 삭제
            - d\[커서 이동\] : 커서 이동하는 만큼 삭제
        - 수정
            - r : 커서가 위치한 부분의 문자 하나를 입력하는 문자로 대체
            - u : 작업 취소(Ctrl + z)
        - 복사 및 붙여넣기
            - yy : 커서가 위치한 한 줄을 복사
            - y\[커서이동\] : 커서 이동하는 만큼 복사
            - p : 커서 밑이나 커서 다음에 붙여넣기
            - :\[n1\], \[n2\] co \[n3\] : n1번 줄부터 n2번 줄까지 복사해서 n3번 줄 밑에 붙여 넣기
    
    - Last Line mode 사용
        - 편집기 상태 변경
            - :set nu : 라인 넘버 표시
            - :set nonu : 라인 넘버 표시 안함
            - :set ic : 검색할 때 대소문자 무시
            - :set noic : 검색할 때 대소문자 구분
        - 검색 및 변환
            - /\[내용\] : 내용을 검색함. n으로 다음 검색, N으로 이전 검색
            - :%s/\[찾을내용\]/\[바꿀 내용\]/g : 원본을 수정으로 변경
        - 저장 및 종료
            - :w : 저장
            - :q : 종료
            - :wq : 저장 및 ㅊ종료
            - :w! : 강제로 저장
            - :q! : 강제로 종료
            - :wq! : 저장 및 강제 종료

- 디렉토리 및 파일 검색
    - 파일 내용 검색 : grep, fgrep, egrep ...
        - grep \[옵션\] \[패턴\] \[파일 이름\]
            - 옵션 : -i, -n, -v, -w, -c, -l
            - 정규식 표현 : ^, $, ., *, \[\], \[^\]
        - fgrep : CLI에서 사용하는 여러 특수문자들을 단순한 문자로 인식해서 문서 내에서 해당 특수문자를 찾을 때 사용

    - 파일 도는 디렉토리 검색 : find
        - find \[경로\] \[조건\] \[아규먼트\] \[행동\]
            - 예시 : find / -name ipconfig
            - 조건
                - -name : 이름으로 검색
                - -type : 파일의 타입으로 검색
                - -perm : 권한으로 검색
                - -user : 소유자로 검색
                - -size : 파일 크기로 검색
                - -atime : 파일의 마지막 접근 시간으로 검색
                - -utime : 파일의 마지막 수정 시간으로 검색
            - 행동
                - -ls : 자세한 결과 출력
                - -exec \[명령어\] {} \; : 검색한 파일을 턱정 명령어로 실행
                - -exec rm -rf {} \; : 제거를 위한 행동

- 링크
    - 특정 파일 또는 디렉토리에 접근을 쉽게할 수 있도록 하는 방법
    - //링크 이미지 삽입 필요합니다.//
    - 하드링크
        - 디스크에 저장되어 있는 파일 또는 디렉토리의 위치가 동일한 곳을 가리키고 있는 것, 윈도우에서 일반적인 파일 운영체제 자체가 시스템을 관리할 때 사용하는 파일 이름은 컴퓨터가 알아보기 쉬운 파일이름으로 되어있다. 하지만 컴퓨터가 알아보기 쉬운 이름은 사람들이 이용할 때 알아보기 힘들기 때문에 사람들이 알아보기 쉬운 이름의 하드링크 파일을 이용해서 파일에 접근하도록 만든 것이다.
        - ln \[원본\] \[하드링크\]
    - 심볼릭 링크
        - 파일 또는 디렉토리를 가리키고 있는 것, 윈도우에서 바로가기
        - ln -s \[원본\] \[하드링크\]


- 권한
    - UNIX/LINUX 또는 윈도우의 모든 파일과 디렠토리는 권한들의 집합으로 구성되어 있다. LINUX나 윈도우는 여러 명의 사용자가 동시에 사용 가능한 다중 사용자 기능을 지원하기 때문에 권한이 굉장히 중요하다. 권한은 기본적으로 모든 파일과 디렉토리에 대해 읽기, 쓰기, 실행 작업에 대한 접근 여부를 결정한다.

    - 권한의 종류

        |drwxr-xr-x|3|root|root|18|9월 28 22:07|.config|
        |:---:|:---:|:---:|:---:|:---:|:---:|:---:|
        |(1)|(2)|(3)|(4)|(5)|(6)|(7)|
        1. 권한 및 파일의 종류
        2. 하드 링크 수
        3. 소유자
        4. 관리그룹
        5. 파일 크기
        6. 마지막 수정 시간
        7. 파일 이름

    - 파일 및 디렉토리 관련 명령어

    ||r|w|x|
    |:---:|:---:|:---:|:---:|
    |파일 명령어|cat, more, head, tail|vi편집기에 저장|파일의 이름|
    |디렉토리 명령어|ls|mkdir, mv, touch, rm|cd|

    - 권한의 변경
        - 심볼릭 모드
            
        |이름||이름||이름||
        |:---:|:---:|:---:|:---:|:---:|:---:|
        |소유자|u|읽기|r|권한 부여|+|
        |관리그룹||쓰기|w|권한 회수|-|
        |나머지||실행|x|||

        - 8진수 모드
            - read : 4, write : 2, exec : 1

        |0|1|2|3|4|5|6|7|
        |:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
        |- - -|- - x|- w -|- w x|r - -|r - x|r w -|r w x|

- 특수 권한 ----- 추가 설명 필요합니다...
    - SetUID
        - 나머지 사용자가 파일을 실행할 때 소유자의 권한으로 접근할 수 있게 해주는 권한
    - SetGID
        - 나머지 사용자가 파일을 실행할 때 관리 그룹의 권한으로 접근할 수 있게 해주는 권한
    - StickyBit
        - 디렉토리에 부여하는 권한, 디렉토리를 마치 자유게시판처럼 사용할 수 있게 해주는 권한  
            (일반적으로 /tmp 디렉토리에 부여)

- 쉘 명령어 사용
    - Shell
        - 터미널에 입력한 명령을 해석하고 관리하는 프로그램
        - 쉘은 사용자 커널 사이에 연결시켜주는 역할을 하며 사용자가 입력한 명령을 해석하여 운영체제가 해당 명령을 알아들을 수 있게 해준다.
        - 쉘은 여러가지 종류가 있으면 가장 많이 사용되는 쉘은 Bash(Born Again Shell)이다.

    - 쉘 메타문자 사용
        - ~ : 현재 로그인한 사용자의 홈 디렉토리
        - \- : 이전 작업 디렉토리
        - \* : 하나 이상의 문자를 대체하는 문자, 일반적으로 전체를 의미
        - ? : 하나의 문자만 대체
        - \`\` : 안에 있는 문자를 명령어로 인식하여 실행되게 한다. 명령어라면 실행된다.         
        - '' : 작은 따옴표 안에 있는 모든 메타문자를 일반문자로 취급한다.
        - "" : 큰 따옴표 안에 있는 $, `, \ 문자를 제외한 나머지 문자만 일반문자로 취급한다.
    - 쉘 메타문자 사용 :: 방향 재지정 메타문자 : <, >, |
        - < : 표준 입력 재지정
        - \> : 표준 출력 및 표준 에러를 재지정
            - 일반적으로 명령어의 출력을 파일로 저장 또는 네트워크로 전송
            - 파일에 저장할 때 : echo "test" > ./file
            - 정상적인 결과만 출력할 때 : find / -perm -4000 2> /dev/null
            - 에러 결과만 출력할 때 : find / -perm -4000 1> /dev/null
            - 정상적인 결과는 파일에 저장, 에러는 출력 X : find / -perm -4000 1> ./setuid_file 2> /dev/null
            - \>을 한번만 사용하면 파일의 내용을 덮어씀, \>\>을 사용하면 기존의 파일 내용에 이어서 씀
        - | : 파이프 문자
            - ls /etc | grep rc : ls 명령어의 결과에서 특정 문자를 포함한 라인만 뽑아 볼 때
            - ls /etc | grep yum : ls 명령어의 결과에서 yum문자를 포함한 라인만 뽑아 볼 때
            - cat file | grep bored : cat 명령어의 결과에서 bored문자를 포함한 라인만 뽑아 볼 때
            - ls /etc | more : ls의 결과가 너무 길어서 화면에 다 안나와 끊어서 보고싶을 때
    - 사용자 초기화 파일
        - /etc/profile : 시스템 전역에 걸쳐 환경을 설정하는 파일
        - ~/.profile : 개별 사용자의 홈 디렉토리에 있는 파일(사용자 설정)
        - ~/.bashrc : 개별 사용자의 홈디렉토리에 있는 파일(쉘 관련)
        - 환경 변수, 별명 기능(alias), 쉘 옵션 정의 등 설정 가능
        
        - 환경 변수 : 시스템 환결에 대한 정보를 저장
            - HOME : 사용자의 홈디렉토리
            - PATH : 실행파일을 찾는 경로
            - LANG : 프로그램 사용시 기본 지원되는 언어
            - SHELL : 로그인해서 사용하는 쉘
            - EDITOR : 기본 편집기의 이름
            - PS1 : 명령 프롬프트 변수

- 프로세스 제어
    - 프로세스 : 실행중인 프로그램
    - 상황에 따라 명칭이 달라짐
        - 부모 프로세스
            - 다른 프로세스를 생성할 수 있는 프로세스
        - 자식 프로세스
            - 부모 프로세스로부터 만들어지는 프로세스
        - 데몬 프로세스
            - 일반적으로 사용자가 실행시키지 않고 커널에의해 구동, 백그라운드로 동작
            - 특정 서비스를 제공하기 위해 구동
            - 파일 이름 끝에 'd'를 붙여서 사용하는 것이 일반전
            - Windows의 서비스와 비슷한 존재
        - 고아 프로세스
            - 일반적으로 자식 프로세스는 종료되면 부모 프로세스로 되돌아 가는데 부모 프로세스가 먼저 종료된 경우에 자식 프로세스를 고아 프로세스라고 한다.
            - 고아 프로세스는 init 프로세스가 처리해준다.
            - 현재는 systemd 프로세스가 처리해준다.
        - 좀비 프로세스
            - 정상적으로 프로세스를 종료했지만 자원을 반납하지 않은 상태로 계속 남아있는 상태
            - 자원을 점유한 상태에서 동작하지 않는 프로세스

    - ps 명령어 :: 작업관리자
        - ps -ef를 많이 쓴다.(&로 백그라운드로 실시할 수 있다.)
        - 명령어 옵션 PNG 삽입 위치
        - pstree, pgrep, top
        - 시그널 번호
            - 시그널 번호 PNG 삽입 위치
        - kill, pkill :: 프로세스 종료
            - kill : pid로 지정
            - pkill : process 이름으로 지정
        
- 압축 및 아카이브
    - 아카이브
        - tar cvf \[아카이브 파일\] \[묶을 파일1\] \[묶을 파일2\] ...
            - 아카이브 생성
        - tar xvf \[아카이브 파일\]
            - 아카이브 해제
        - tar tvf \[아카이브 파일\]
            - 아카이브 내용 보기
    - 압축
        - zip, gzip, bzip2
        
        |종류|압축|압축 해제|
        |:---:|:---:|:---:|
        |zip|zip \[압축 파일 이름\] \[압축할 파일 이름\] ...|unzip \[압축 파일 이름\]|
        |gzip|gzip \[압축 파일 이름\]|gunzip \[압축 파일 이름\]|
        |bzip2|bzip2 \[압출 파일 이름\]|bunzip2 \[압축 파일 이름\]|

    - 아카이브와 압축
        - tar zcvf \[이름.tar.gz\] \[묶을 파일1\] \[묶을 파일2\] ...
        - tar zxvf \[이름.tar.gz\]
        - tar jxvf \[이름.tar.bz2\]