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
- display : block, inline, inline-block 차이
   *block : 한 줄 모두 차지 / inline : 콘텐츠 크기 만큼만 차지
  - display: inline / 전후 줄바꿈 없이 한 줄에 다른 엘리먼트들과 나란히 배치
     *width와 height 속성을 지정해도 무시, margin과 padding 속성은 좌우 간격만 반영이 되고, 상하 간격은 반영이 되지 않음
  - display : block : 지정된 엘리먼트는 전후 줄바꿈이 들어가 다른 엘리먼트들을 다른 줄로 밀어내고 혼자 한 줄을 차지 
     *width, height, margin, padding 속성이 모두 적용됨
  - display : inline-block : inline 엘리먼트처럼 전후 줄바꿈 없이 한 줄에 다른 엘리먼트들과 나란히 배치되지만, block 엘리먼트처럼 width와 height 속성 지정 및 margin과 padding 속성의 상하 간격 지정이 가능
    ```css
    .clearfix::after{
      content: "";
      clear: both;
      display: block;    }
  ```
- float 속성
  - linebox 안에서 왼쪽 또는 오른쪽으로 배치
  - normal flow를 벗어나서 화면에 떠있는 형태로 배치
  - float 요소의 부모에게 display: flow-root를 지정해서 float 개체의 높이를 부모가 읽어들일 수 있도록 할 수 있음.
  - overflow: hidden 또는 clear: both 를 활용하여 float 이슈를 해결할 수도 있음

- position 속성 : relative, absolute
  - 사용법 : 기준을 잡고(relative, absolute) => 이동시킴(top, bottom, left, right사용, ex, top:50px;)
  - 참고사이트 : https://creamilk88.tistory.com/197
  
  - relative : 요소 자기 자신의 위치를 기준으로, only 자기 자신만 이동 배치
    - 요소 자기 자신의 원래 위치(static일 때의 위치)를 기준으로 배치한다.
    - 원래 위치를 기준으로 위쪽(top), 아래쪽(bottom), 왼쪽(left), 오른쪽(right)에서 얼마만큼 떨어질 지 결정한다.
    - 위치를 이동하면서 다른 요소에 영향을 주지 않는다.
    - 문서 상 원래 위치가 그대로 유지된다.

  - absolute : 부모(조상) 요소를 기준으로 배치
     *parent(부모 요소)가 child(자식 요소)의 기준점이 됨 
    - 가장 가까운 위치에 있는 조상 요소를 기준으로 배치한다.
    - 조상 요소 위치를 기준으로 위쪽(top), 아래쪽(bottom), 왼쪽(left), 오른쪽(right)에서 얼마만큼 떨어질 지 결정한다.
    - 조상 중 Position을 가진 요소가 없다면 초기 컨테이닝 블록(<body>요소)를 기준으로 삼는다. (static을 제외한 값)
    - 문서 상 원래 위치를 잃어버린다. (아래에 있는 div가 해당 자리를 차지한다)
   ```bash
   다음 html 코드로 아래의 경우들을 확인해보자.
   <div class="grand-parent">
    <div class="parent">
        <div class="child">1</div>
        <div class="child absolute">2</div>
        <div class="child">3</div>
    </div>
   </div>

   <  부모 relative & 자식 absolute, Parent에게 Position 값이 있는 경우>
    Parent의 위치를 기준으로 삼는다.
     .parent {
      /* .. */
      /* .. */
      /*  parent(부모 요소)가 child(자식 요소)의 기준점이 됨 */
       position: relative;

     /*  position : absolute */
    .absolute {
     /* 부모 요소인 parent를 기준으로 위치가 결정된다. */
      position: absolute;
      bottom: 5px;
      right: 5px;
    }
     **아래 배치화면**    
    1
    3

                      2
   ``` 

## Emmet 단축키 설정
- 설정 -> 바로가기 키 -> emmet 약어로 래핑에 단축키 등록 (Ctrl + Alt + W)
- 설정 -> 바로가기 키 -> emmet 수식 평가 (Ctrl + Alt + M)

```bash
ul.member-service>li*>span[aria-hidden="true"]{:}+a[href="/"]
```

