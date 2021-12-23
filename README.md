# git_vs_svn

## 형상 관리 도구 = 버전 관리 도구

- 형상관리는 소스의 변화를 끊임없이 관리하는 것을 말함

- 소스 코드를 USB나 메일로 주고받는 건 자원적 낭비 및 보안문제

 - 소스를 버전 별로 관리할 수 있어서 개발할 때 실수로 소스를 삭제하거나, 수정하기 이전으로 돌아가야되는 경우 유용하게 사용되는 툴

 - 또한 팀 프로젝트에서도 누가 무엇을 어떻게 수정했는지도 알 수 있기 때문에 코드를 병합하거나 수정된 소스를 추적하는 데에도 쓰임

 - Git과 SVN을 많이 씀


------

## Git
### Git Repository에 대한 원격 액세스를 제공하는 서비스
- Git-hub(Microsoft)
- Git-lab(Gitlab Inc.)
- Bitbucket(Atlassian)
<!-- ### Git-hub 무료 계정 vs Pro 플랜 계정

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
         - 저장소 인사이트 -->


### Git bash vs Git gui vs Sourcetree
- git bash는 CLI환경으로 명령어를 사용하여 git을 사용함
- git gui는 다양한 명령어를 GUI로 시각화하여 쉽게 git을 사용하기 위한 도구(GIT 기본 프로그램)
- Sourcetree는 다양한 명령어를 GUI로 시각화하여 쉽게 git을 사용하기 위한 도구(Jira, Trello를 개발사인 Atlassian)

### Git Flow
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

        1. 일단 master 브랜치에서 시작을 합니다.
        2. 동일한 브랜치를 develop에도 생성을 합니다. 개발자들은 이 develop 브랜치에서 개발을 진행합니다.
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


------
## SVN

### TortoiseSVN
- 버전 관리 도구

### Visual SVN Server Manager
- github, gitlab 처럼 원격 repository를 생성
- repository 접근 계정 및 권한 설정

### SVN 용어

trunk(= git main/master)

- 프로젝트에서 가장 중심이 되는 디렉토리

- 모든 프로그램의 개발 작업은 Trunk 디렉토리에서 이루어 집니다.

- trunk 디렉토리 바로 아래에는 소스들의 파일과 디렉토리가 들어가게 됩니다.

- 단어 자체의 뜻은 mainLine 과 동일한 뜻

Update(= git pull = fetch + merge)

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

commit
- git은 로컬저장소에 저장(push가 원격에 저장)
- svn은 원격저장소에 저장

checkout
- git은 작업 브랜치로 이동하는 것을 의미
- svn은 로컬저장소와 원격저장소를 연결(= git remote)



### Git 사용 예시
1. Project 선정 및 Clone

2. Git-flow에 따른 사용

3. Conflict가 없으면 브랜치 병합(Merge) 혹은 Pull Request

4. Conflict가 있으면 해결 후 브랜치 병합(Merge) 혹은 Pull Request

5. push 권한이 없는 프로젝트라면 Folk후 2~4 반복

5. Folk후 pull request

### svn 사용 예시
1. Visual SVN Server 만들기

2. 개발한 것 Server에 import

3. 다른 협업자가 Server Checkout

4. 다른 협업자가 일을 함

5. commit(깃에서는 push)

6. conflict 해결

7. 다시 커밋

8. update



## 결론

![git_svn 도식](https://github.com/knowmetoowell/git_vs_svn/blob/main/img/git_svn%20%EB%8F%84%EC%8B%9D.png "Git-flow 도식화")

![검색량 추이](https://github.com/knowmetoowell/git_vs_svn/blob/main/img/git_svn%20%EA%B2%80%EC%83%89%EB%9F%89%20%EC%B6%94%EC%9D%B4.png "Git-flow 도식화")