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