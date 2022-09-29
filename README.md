# 업무에 바로쓰는 HTML5/CSS3

## 환경구성
- 최신 웹브라우저 및 확장 프로그램 설치
  - visbug
  - tota11y
  - web developer
  - headingsmap
  - open wax
- Visual Studio Code  설치 및 확장 프로그램 설치
  - live-server
  - auto rename tag
  - auto close tag
  
- [node 설치](https://nodejs.org/ko/) : LTS 버전
- [git 설치](https://git-scm.com/) : 최신 버전

## Git를 사용하여 소스코드 version 관리하기
 - (1) online github에 repository 생성하기
 ```bash
   - (방법1)기존 repository 복제 : github's 해당 repository로 이동 => Fork 클릭
   - (방법2)새로 생성 : new repository 클릭
```
 - (2) Local에 repository 생성하기(git bash 명령창에서 수행)  
 ```bash
   - 위(1)의 github repository 주소 복사 : github's repository => code => https에서 주소 복사 
   - git bash terminal에서 repository를 다운로드 할 local 폴더로 이동
   - git clone https_address <= 명령 수행하면 local에 github's repository가 복제됨
 ```
 - (3) github의 계정정보 등록(아래 명령 2개 수행 : github에 등록한 정보를 정확히 입력)  
 ```bash
   - git config --global user.name "내 이름"
   - git config --global user.email "내 메일 주소"   
```
 - (4) remote(online github repository)의 별칭(단축어)설청하여 원격등록을 위한 준비하기 
 ```bash 
   - cd local_repository : bash에서 위(2)에서 생성된 local's repository로 이동
   - git remote add nickname_of_remoterepository httpsaddress_of_remoterepository
    =>ex) git remote add rehtml https://github.com/johumsai/webcafeHTML5.git
       *rehtml = https://github.com/johumsai/webcafeHTML5.git 동일
       
   - git remote : 이 명령어로 등록한 별칭 확인!
   - git remote -v : 등록한 별칭 + 설정된 원격지 repository https주소 확인!
```
 - (5) local에서 변경한 파일을 원격지인 github's repository에 등록하여 source code 버전관리하기
 ```bash
   - git status : 이 명령어로 local files의 현재 상태 확인(color로 구분됨)
   - git add <file_name> : 마지막에 명시한 local 파일만 remote github로 추가할 준비를 함
   - git add . : 현재 모든 local 파일을 remote github로 추가할 준비를 함
       *git add : Index Area 영역으로 이동하는 명령어

   - git commit -m "커밋 메시지" : 변경이력에 대한 확정파일 생성, 메시지는 변경사항에 대한 설명주석
   - git push rehtml main : 원격github's repository에 실제 등록, rehtml은 remote, main은 local

   - git log --oneline : 변경이력 조회, 한줄(oneline) 단위로 각각의 그간의 변경이력 확인
```
```bash
## 참고 
  - [강사 저장소 Fork](https://github.com/seulbinim/webcafeHTML5)
  - Fork한 저장소를 컴퓨터(Local)로 [Clone](https://github.com/seulbinim/webcafeHTML5.git)  
  - git clone https://github.com/seulbinim/webcafeHTML5.git
```

## 레이아웃 구성하기
- display: flex
  - flex-direction 속성으로 row 또는 column 방향을 지정할 수 있음.
  - flex-direction에 따라 메인축과 교차축이 결정됨.
  - 플렉스 컨테이너와 플렉스 아이템이 가질 수 있는 속성이 다름.
- float 속성
  - linebox 안에서 왼쪽 또는 오른쪽으로 배치
  - normal flow를 벗어나서 화면에 떠있는 형태로 배치
  - float 요소의 부모에게 display: flow-root를 지정해서 float 개체의 높이를 부모가 읽어들일 수 있도록 할 수 있음.
  - overflow: hidden 또는 clear: both 를 활용하여 float 이슈를 해결할 수도 있음
  ```css
    .clearfix::after{
      content: "";
      clear: both;
      display: block;    }
  ```

## Emmet 단축키 설정
- 설정 -> 바로가기 키 -> emmet 약어로 래핑에 단축키 등록 (Ctrl + Alt + W)
- 설정 -> 바로가기 키 -> emmet 수식 평가 (Ctrl + Alt + M)

```bash
ul.member-service>li*>span[aria-hidden="true"]{:}+a[href="/"]
```

