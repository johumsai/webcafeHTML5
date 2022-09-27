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

## Git 버전 관리
- [강사 저장소 Fork](https://github.com/seulbinim/webcafeHTML5)
- Fork한 저장소를 컴퓨터(Local)로 [Clone](https://github.com/seulbinim/webcafeHTML5.git)  
```bash
git clone https://github.com/seulbinim/webcafeHTML5.git
```

- 변경 이력 및 상태 확인
```bash
git status
```
- Index Area 영역으로 이동
```bash
git add <파일명>
```
```bash
git add .
```
- 변경 이력에 대한 확정본 생성
```bash
git commit -m "커밋 메시지"
```
- remote 저장소로 백업
```bash
git push origin main
```
- 변경 이력 조회(로그 확인)
```bash
git log --oneline
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
      display: block;
    }
  ```

## Emmet 단축키 설정
- 설정 -> 바로가기 키 -> emmet 약어로 래핑에 단축키 등록 (Ctrl + Alt + W)
- 설정 -> 바로가기 키 -> emmet 수식 평가 (Ctrl + Alt + M)

```bash
ul.member-service>li*>span[aria-hidden="true"]{:}+a[href="/"]
```

