# git_vs_svn

## 형상 관리 도구 = 버전 관리 도구

- 형상관리는 소스의 변화를 끊임없이 관리하는 것을 말함

- 소스 코드를 USB나 메일로 주고받는 건 자원적 낭비 및 보안문제

 - 소스를 버전 별로 관리할 수 있어서 개발할 때 실수로 소스를 삭제하거나, 수정하기 이전으로 돌아가야되는 경우 유용하게 사용되는 툴

 - 또한 팀 프로젝트에서도 누가 무엇을 어떻게 수정했는지도 알 수 있기 때문에 코드를 병합하거나 수정된 소스를 추적하는 데에도 쓰임

 - Git과 SVN을 많이 씀

## 버전 관리 시스템

### 로컬 버전 관리

- 로벌 버전 관리 시스템은 간단한 데이터베이스를 이용해 파일의 이력(변경 정보)를 관리하는 시스템

- 협업을 해야 하는 상황에서는 로컬 버전 관리 시스템으로의 버전 관리가 쉽지 않다. 



### 중앙집중식(SVN) 

- SVN은 로컬에서 Commit을 수행하면 바로 중앙 저장소에 반영이 된다. 

- commit한 내용에 문제가 있을 경우 다른 개발자들에게 바로 영향을 미치게 된다.

- 개발자가 자신만의 version history를 가질 수 없다.

- 모든 버전 관리 관련 동작은 서버에서 처리되어야 하므로 서버의 부하가 크다.

- 서버가 다운되거나 장애가 발생하면 버전 관리가 이루어지지 않는다.

- 오프라인 상태에서는 버전 관리 시스템을 사용할 수 없다.

- 모든 버전 관리 관련 동작은 적어도 한 번 서버를 경유해야 하므로 속도가 느리다. 

- 로그를 보는 것 조차 서버에서 데이터를 받아와야 하므로 느리다.

- 서버에서 데이터가 망가지거나 삭제되면 복구하기 매우 어렵다.

- 대부분의 기능을 완성해놓고 소스를 중앙 저장소에 commit

- 직관적인 사용법을 지원하기 때문에 단순한 버전 관리에 유용함

- 브랜치/태그 등의 기능을 사용하기 비교적 어려움




### 분산관리식(Git)
- Git은 로컬에서 Commit을 수행하면 로컬 저장소에 반영이 된다.

- 개발자는 마음대로 commit을 수행하며 자신이 원하는 순간에 서버에 변경 내역(commit history)을 Push를 하면 원격 저장소에 반영이 된다.

- 서버의 통합 관리자는 관리자가 원하는 순간에 각 개발자의 commit history를 가져올 수 있음.

- 개발자가 자신만의 commit history를 가질 수 있으며, 개발자와 서버의 저장소는 독립적으로 관리

- 오프라인 환경에서도 로컬저장소에 commit하면 되고 로그를 볼 수 있음.

- 저장소를 히스토리와 더불어 전부 복제하기 때문에 서버에 문제가 생겨도 로컬에서 작업이 가능

- 중앙 집중식 버전 관리 시스템에 비해 복잡하다

- 브랜치/태그 등의 기능을 사용하기 편함

- 대부분의 버전 관리가 로컬에서 이루어지므로 속도가 빠르다.

로컬 버전관리
![로컬 버전 관리](https://github.com/knowmetoowell/git_vs_svn/blob/main/img/%EB%A1%9C%EC%BB%AC%20vcs%20.png)

---------------------------------------
중앙집중식
![중앙집중식](https://github.com/knowmetoowell/git_vs_svn/blob/main/img/%EC%A4%91%EC%95%99%EC%A7%91%EC%A4%91%EC%8B%9D.png)

svn
![svn 도식](https://github.com/knowmetoowell/git_vs_svn/blob/main/img/svn_%EB%B0%A9%EC%8B%9D.png)

-----------------------------------------------------------------------

분산관리식
![분산관리식](https://github.com/knowmetoowell/git_vs_svn/blob/main/img/%EB%B6%84%EC%82%B0%EA%B4%80%EB%A6%AC%EC%8B%9D.png)

git
![git 도식](https://github.com/knowmetoowell/git_vs_svn/blob/main/img/git_%EB%B0%A9%EC%8B%9D.png)




------

## Git
### 필요한 설치 프로그램
- git

        버전 관리 툴, svn에 비해 기능이 다양함

- Git bash vs Git gui vs Sourcetree(Git client)
       
        git bash는 CLI환경으로 명령어를 사용하여 git을 사용함(GIT 기본 프로그램)
        git gui는 다양한 명령어를 GUI로 시각화하여 쉽게 git을 사용하기 위한 도구(GIT 기본 프로그램)
        Sourcetree는 다양한 명령어를 GUI로 시각화하여 쉽게 git을 사용하기 위한 도구(Jira, Trello를 개발사인 Atlassian)

- git 설치 및 기능 참고 -https://devrappers.tistory.com/category/Git

### Git Repository에 대한 원격 액세스를 제공하는 서비스
- Git-hub(Microsoft)

        가장 많이 사용하기 때문에 접근성이 좋음
        github action이라는 CI/CD 툴 제공
        속도와 안정성이 가장 좋음

- Git-lab(Gitlab Inc.)

        가격 정책이 가장 좋음
        CI/CD를 위한 기능이 잘 되어있음
        리눅스 설치형 프로그램이 무료임
        속도가 느리고 안정성이 불안함

- Bitbucket(Atlassian)

        다른 버전관리 툴과 호환성이 좋음
        JIRA, Trello와 같은 DevOps tool 제공(같은 회사 제품)
        속도와 안정성은 무난함

Git-hub 무료 계정 vs Pro 플랜 계정

- Public 저장소에서는 무료 계정과 Pro 플랜 계정의 차이가 거의 없음
- GitHub Actions 사용 시간이 월 2,000분에서 3,000분으로
- GitHub Packages 용량이 500MB에서 2GB로 늘어남
- Private 저장소에서 무료 계정은 다음과 같은 기능을 사용할 수 없음

        Email을 통한 지원
        3,000분/월 GitHub Actions
        2GB GitHub Packages 스토리지
        비공개 저장소에서 고급 기능 이용 가능
         - 풀 리퀘스트 리뷰 강제
         - 다수의 풀 리퀘스트 리뷰어 지정 가능
         - 자동 링크 레퍼런스
         - 깃허브 페이지
         - 위키
         - 보호된 브랜치 기능
         - 코드 소유자(Code owners)
         - 저장소 인사이트-->




### Git Flow - 깃 사용을 위한 방법론
- Git-flow는 Git이 새롭게 활성화되기 시작하는 쯤에 Vincent Driessen이라는 사람의 블로그 글에 의해 널리 퍼지기 시작했고 현재는 Git으로 개발할 때 거의 표준과 같이 사용되는 방법론
- 즉, Git-flow는 기능이 아니고 서로간의 약속인 방법론
- Git-flow가 완벽한 방법론은 아니고 각자 개발 환경에 따라 수정하고 변형해서 사용
- Git-flow는 총 5가지의 브랜치를 사용해서 운영
        
        master : 기준이 되는 브랜치로 제품을 배포하는 브랜치
        develop : 개발 브랜치로 개발자들이 이 브랜치를 기준으로 각자 작업한 기능들을 Merge
        feature : 단위 기능을 개발하는 브랜치로 기능 개발이 완료되면 develop 브랜치에 Merge
        release : 배포를 위해 master 브랜치로 보내기 전에 먼저 QA(품질검사)를 하기위한 브랜치
        hotfix : master 브랜치로 배포를 했는데 버그가 생겼을 떄 긴급 수정하는 브랜치
        
- master와 develop가 중요한 매인 브랜치이고 나머지는 필요에 의해서 운영하는 브랜치

- Git-flow 도식화 

![Git-Flow](https://github.com/knowmetoowell/git_vs_svn/blob/main/img/git-flow.png "Git-flow 도식화")

        1. master 브랜치에서 시작을 합니다.
        2. 동일한 브랜치를 develop에도 생성합니다. 개발자들은 이 develop 브랜치에서 개발을 진행합니다.
        3. 개발을 진행하다가 회원가입, 장바구니 등의 기능 구현이 필요할 경우 A개발자는 develop 브랜치에서 feature 
        브랜치를 하나 생성해서 회원가입 기능을 구현하고 B개발자도 develop 브랜치에서 feature 브랜치를 하나 생성해
        서 장바구니 기능을 구현합니다.
        4. 완료된 feature 브랜치는 검토를 거쳐 다시 develop 브랜치에 합칩니다.(Merge)
        5. 이제 모든 기능이 완료되면 develop 브랜치를 release 브랜치로 만듭니다. 그리고 QA(품질검사)를 하면서 보
        완점을 보완하고 버그를 픽스합니다.
        6. 모든 것이 완료되면 이제 release 브랜치를 master 브랜치와 develop 브랜치로 보냅니다. master 브랜치에서 
        버전추가를 위해 태그를 하나 생성하고 배포를 합니다.
        7. 배포를 했는데 미처 발견하지 못한 버그가 있을 경우 hotfixes 브랜치를 만들어 긴급 수정 후 태그를 생성하
        고 바로 수정 배포를 합니다.


### Git-hub Branch vs Fork
- 브랜치(Branch)

1. 하나의 원본저장소에서 분기를 나눕니다.

2. 하나의 원본저장소에서 코드 커밋 이력을 편하게 볼 수 있습니다.

3. 다수의 사용자가 다수의 브랜치를 만들면 관리하기가 힘들 수 있습니다.<br>

- 포크(fork)

1. 여러 원격저장소를 만들어 분기를 나눕니다.

2. 원본저장소에 영향을 미치지 않으므로 마음껏 코드를 수정할 수 있습니다.

3. 원본저장소의 이력을 보려면 따로 주소를 추가해줘야 합니다.

### Git-hub pull request
- 수정한 내역이 있으니 나의 branch를 검토 후 병합을 요청하는 것

- 코드 충돌을 최소화할 수 있고 push 권한이 없는 오픈 소스 프로젝트에 기여할 때(Fork) 많이 사용

----------
## Windows git server 구축

- 웹(github 등)상에 소스코드를 올리고 싶지않고 개인 서버에 원격 저장소를 구축하고 싶을 때.

### 설치 필요 프로그램
- Git for Windows
        
        버전 관리 툴
        라이센스: MIT
        다운로드: http://git-scm.com
- Bonobo Git Server
        
        서버 관리 툴
        라이센스: MIT
        다운로드: http://bonobogitserver.com

- Microsoft .NET Framework 4.5
        
        Bonobo Git Server 실행을 위해 필요함(해당 PC에 미 설치된 경우 설치)
        다운로드: https://www.microsoft.com/ko-kr/download/details.aspx?id=30653

- git 클라이언트

        git 클라이언트 GUI 툴 (CLI가 편하면 설치하지 않아도 됨)
        종류: sourcetree, tortoiseGit, Git-fork, git Kraken, github desktop 등
        



### Bonobo Git Server

1. IIS 설치

![IIS 설치](https://github.com/knowmetoowell/git_vs_svn/blob/main/img/%ED%99%94%EB%A9%B4%20%EC%BA%A1%EC%B2%98%202021-12-28%20094507.png)

참고: https://offbyone.tistory.com/301

2. Bonobo Git Server 설치

        다운로드 받고 압축 해제
        압축 해제한 파일을 웹 서비스 디렉토리에 복사
        기본 디렉토리: C:\inetpub\wwwroot
        기본 디렉토리 및에 git 이란 디렉토리를 생성 후 복사(디렉토리 명은 개인 취향대로 생성)

3. IIS 설정

![IIS 설정](https://github.com/knowmetoowell/git_vs_svn/blob/main/img/iis%EC%84%A4%EC%A0%95.png)

4. Bonobo Git Server 접속

        http://127.0.0.1/설정한서버이름 혹은 http://IP주소/설정한서버이름
        기본 관리자 계정: admin / admin

<br>




### git client 비교

- sourcetree
        
        -장점
        
        직관적인 UI
        한글 패치 - 한국 유저가 Git을 입문하기 쉬워 한국 한정 점유율이 높다.
        -> 커뮤니티가 잘 형성되어 있음
        시각화- marge, branch등 시각화가 아주 잘 되어있다.
        무료 사용

        -단점

        줄수가 많은 파일을 미리 볼 때 느림
        계정 인증 변경이 어려움
        이미지 뷰어 제공안함
        안정성이 불안함 
        Linux지원 안함

- tortoiseGit

        장점: TortoiseSVN 의 소스를 기반으로 개발되어 기존 Tortoise 사용자라면 UI 가 친숙함
        단점: 기능 및 안정성이 부족함, windows 전용, 직관성이 부족함

- Git-fork

        - 장점
        안정성이 좋음 
        가볍고 빠름 
        1회성 구매(구매 안해도 큰 차이 없음)
        충돌이 발생할 경우 ui를 통해 보기가 쉬움
        이미지 뷰어 제공
        직관적인 UI
        블랙테마 지원
        가로 세로 모드 지원
        꾸준한 업데이트

        - 단점
        Linux지원 안함
        한글 지원 안함

- Git-Kraken

        - 장점
        안정성이 좋음
        가볍고 빠름
        간단히 클릭만으로 commit comment를 수정할 수 있다.
        직관적인 UI
        다양한 자체 기능을 제공(redo/undo 등)
        푸시하지 않은 커밋이나 체크아웃, 커밋 메시지 편집 등을 쉽게 undo 할 수 있다
        드래그&드랍을 이용한 merge

        - 단점
        private 저장소 사용시 월 구독료 내야함(git-hub pro 계정일 때 무료)
        이미지 뷰어 지원 안함
        한글 지원 안함

- Github desktop

        - 장점 
        github 사용시 효율이 좋음
        가볍고 빠름
        
        - 단점        
        브랜치의 내용 파악이 어렵다
        

- SmartGit

        - 장점
        리눅스에서 유용함
        성능이 우수하다

        - 단점
        상용 목적으로 사용할 시 라이센스 구입해야 함
        UI가 직관적이지 못하다

- git extension

        - 장점
        리눅스에서 유용함
        성능이 우수하다
        한글 지원

        - 단점
        초기 설정이 어려움
        UI가 직관적이지 못하다


### git stash란?

- 로컬에서 작업한 소스 내용을 임시로 다른 곳에 저장하는 기능
        
- 현재 작업하고 있는 내용이 있는데 급하게 요청 온 내용이 있어서 현재 내용을 임시로 저장해놓고 급하게 요청 온 건만 올리고(push) 싶을 때 사용




## bonobo git server port 부여

https://offbyone.tistory.com/417

## 제어판\사용자 계정\자격 증명 관리자 => git 자격증명

https://yunseul-light.blogspot.com/2017/08/github-windows-git.html
------------



------
### Git 사용 예시


1. 장바구니기능 요구사항이 생김

2. Feature/basket branch 생성

3. basket 작업중

4. 회원관리 요구사항이 생김

5. basket commit or stash

6. Feature/member_manager branch 생성

7. member_manager 작업

8. member_manager commit

9. Feature/member_manager 작업완료

10. Feature/member_manager develop merge

11. basket 작업완료

12. basket commit

13. Feature/basket 작업완료

14. basket이 develop에 merge될때 member_manager 와의 충돌 발생 가능성 있음(branch간 충돌)

15. 충돌이 발생할경우 conflict 해결

16. develop merge

17. release/v1 branch 생성

18. 수정사항이 있다면 수정

19. develop/master에 release/v_1 merge

20. tag 남기기

21. hotfix/hf_1 생성

22. hf_1 수정

23. develop/master에 hotfix/hf_1 merge

24. tag 남기기

------
### 다른사람이 push하여 충돌이 발생했을 때(같은 브랜치 내에서 협업할 때) 시나리오

1. 같은 원격 저장소 클론

2. 같은 파일 수정 / 다른 파일 수정

3. 하나를 먼저 커밋 푸쉬

4. 나머지 하나 커밋 푸쉬 -> 오류 발생

5. pull을 이용해 최신 상태로 업데이트 -> 같은 파일을 수정 했다면 충돌 발생 

6. 충돌 해결 및 커밋 푸쉬


----------------
## SVN

### 필요한 설치 프로그램
- TortoiseSVN
        
        버전 관리 툴, git에 비해 기능이 적음

- Visual SVN Server Manager
        
        github, gitlab 처럼 원격 repository를 생성
        repository 접근 계정 및 권한 설정

- SVN 설치 및 사용법 참조
https://junspapa-itdev.tistory.com/50

### SVN 용어

Update(= git pull)

- Local의 파일을 Repository와 비교하여 최신 버전의 상태로 갱신한다.

- 동일한 파일을 Repository와 Local에서 동시에 변경한 경우 서브버전에서 자동으로 Merge 해주지만
서브버전에서 Merge를 할 수 없을 경우 Conflict상태로 변경될 수 있다.

- 충돌이 발생하면 사용자에게 Merge 작업을 위임한다.


Revision

- 이름이 의미하듯 수정된 버전을 의미한다. 

- 클라이언트가 Repository에 새로운 파일 또는 파일을 수정하여 commit할 때 마다 revision 번호가 하나씩 증가하게 된다.


HEAD

- Repository에 저장된 최신 revision을 의미한다. 

- 즉 누군가에 의해 가장 최근에 commit된 revision이다.

BASE

- 클라이언트가 checkout 또는 update 명령을 통해 Repository로 부터 내려받은 revision을 의미한다. 

- 이 revision을 기준으로 클라이언트는 수정을하고 commit 하게 된다. 

- commit 시점에 만약 HEAD와 BASE가 다르다면 commit이 거부되고 update를 먼저 수행해야만 commit이 가능하게 된다.

### 깃과 단어는 같지만 다른 동작
commit
- git은 로컬저장소에 저장된 것을 snapshot / 원격 저장소에서의 commit은 원격저장소에 반영됨
- svn은 원격저장소에 저장

checkout
- git은 작업 브랜치로 이동하는 것을 의미
- svn은 로컬저장소와 원격저장소를 연결(= git remote)


### Visual SVN Server 구축

1. http://www.visualsvn.com/server/download/ 에서 서버 프로그램 다운로드 및 설치

2. user 생성 및 group 생성 후 user를 group에 포함

3. repository를 생성하여 그룹에 권한 부여

4. URL를 이용해 확인 -> https://본인컴퓨터IP주소/svn


### svn 사용 예시

0. 환경 구축

1. Visual SVN Server - Repository 만들기

2. 사용자 추가 및 그룹설정, 권한 부여

3. 로컬에서 개발한 것이 있다면 Server에 import

4. svn checkout1  

5. svn checkout2

6. commit -> commit 시점에 만약 HEAD와 BASE가 다르다면 commit이 거부(show log에서 확인가능)

7. conflict 해결

8. 다시 commit

    주기적 update



---------------------------------

## git-svn 비교

### 비교표
![git_svn 비교표](https://github.com/knowmetoowell/git_vs_svn/blob/main/img/git_svn_%EB%B9%84%EA%B5%90%ED%91%9C.png)

### 기능 도식화

![git_svn 도식](https://github.com/knowmetoowell/git_vs_svn/blob/main/img/git_svn%20%EB%8F%84%EC%8B%9D.png)

### 관심도 추이

![검색량 추이](https://github.com/knowmetoowell/git_vs_svn/blob/main/img/git_svn%20%EA%B2%80%EC%83%89%EB%9F%89%20%EC%B6%94%EC%9D%B4.png)


https://devrappers.tistory.com/category/Git


----------------------------------------------------------------

<br>

## SVN



----

