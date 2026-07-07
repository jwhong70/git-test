## GiT ##


* GiT 설치:  https://git-scm.com/downloads

* 설치된 버전 확인: [Windows] 키 + X > Window PowerShell > git --version


# VS Code에서 Git Repository 설정 #

* VS Code는 현재 작업 중인 프로젝트 폴더(Workspace)를 Git Repository로 사용
* 해당 폴더 내에 생성되는 .git이라는 숨김 폴더에 모든 버전 관리 기록이 저장

* Git 폴더 구조 확인/사용법

  1) Repository 생성
    - VS Code에서 파일 > 폴더 열기 > 현재 작업 중인 프로젝트 폴더 선택 >
    - 좌측 메뉴의 [소스 제어] 탭에서 [리포지토리 초기화] 클릭 > 해당 폴더에 .git 폴더가 생성
  
  2) 사용자 이름, 사용자 이메일 등록
    - 터미널에서 git config --global user.name "jwhong70" 입력
    - 터미널에서 git config --global user.email "jwhong70@gmail.com" 입력

  3) 등록된 내용 확인: 터미널에 git config --global --list 입력 

  4) 숨김 폴더 확인
    - 파일 탐색기에서 현재 작업 중인 프로젝트 폴더 안에 .git 폴더가 존재하는지 확인 가능

    - Vs Code의 탐색기에서 숨김 폴더 나타내는 방법
      - [파일] > [기본설정] > [설정] > 
      - 검색 창에서 exclude를 검색 > 
      - Files:Exclude 항목에  **/.git 등의 숨김 처리된 폴더나 파일들이 설정되어 있음
      - 마우스를 올리면 나타나는 [X] 버튼을 클릭해 숨김항목 제거

    - 파일 탐색기에서 숨김 폴더 나타내는 방법
      - 파일 탐색기의 [보기] > [옵션] > [폴더 및 검색 옵션 변경] > 
      - [보기] > 고급 설정: 숨김 파일 및 폴더 > [숨김 파일, 폴더 및 드라이브 표시] 체크

  5) 원격 저장소 연결: 이 폴더를 기반으로 GitHub 등의 원격 저장소와 연동해 버전을 관리


# VS Code에서 GitHub 작업 #


# Remote setting(백업)

* GitHub에 새로운 저장소 생성하기 
  1) 본인의 GitHub에서 All repositories > My repositories > [New repositories] 클릭 >
  2) 새로운 저장소의 이름을 설정 
    - Repository name(예: giti-test), Description(예: git for everyone)
    - Public 선택
  3) [Create Repository] 클릭 > jwhong70/git이라는 새로운 저장소가 생성
  4) 저장소 주소 복사(예: https://github.com/jwhong70/git-test)

* 원격 저장소 추가(Remote setting)
  - [소스 제어]의 [리토지토리]의 현재 리포지토리 이름 옆의 [...] > 
  - [풀, 푸시] > [다음으로 푸시] > [원격 추가] >
  - 복사해 놓은 저장소 주소 붙여넣기 > 원격 이름(예: jwhong-git) 지정

* remote 상태 설정 확인
  - 터미널에서 git remote -v 입력
  - 앞서 생성한 GitHub의 저장소 주소 확인 가능

* 원격 저장소로 푸시(Push)
  - [소스 제어]의 [리토지토리]의 현재 리포지토리 이름 옆의 [...] > 
  - [풀, 푸시] > [푸시]


# Git workflow(Git Area): 기본적으로 3단계로 나눠져 있음

1) Working Directory(Unstage Area)
  - 우리가 현재 작업하고 있는 폴더로 생성, 수정, 삭제한 파일들이 있는 디렉토리

2) Staging Area
  - Index라고도 부르며, 변경사항이 있는 파일들을 선택해 커밋할 수 있도록 지정하는 곳
  - 버전을 만들기 위해 준비 중인 파일들의 스냅샷 데이터가 저장된 곳

3) Git Directory(Local Repository)
  - 파일들이 커밋된 곳으로, 파일들의 변경사항에 대한 스냅샷을 가지고 있는 곳
  - Staging Area를 거쳐 만들어진 버전들이 저장된 곳
