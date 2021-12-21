# git_vs_svn

## 형상 관리 도구 = 버전 관리 도구

- 형상관리는 소스의 변화를 끊임없이 관리하는 것을 말함

- 소스 코드를 USB나 메일로 주고받는 건 자원적 낭비 및 보안문제

 - 소스를 버전 별로 관리할 수 있어서 개발할 때 실수로 소스를 삭제하거나, 수정하기 이전으로 돌아가야되는 경우 유용하게 사용되는 툴

 - 또한 팀 프로젝트에서도 누가 무엇을 어떻게 수정했는지도 알 수 있기 때문에 코드를 병합하거나 수정된 소스를 추적하는 데에도 쓰임

 - Git과 SNV을 많이 씀


------
## Git

### Git-hub
- Microsoft의 자회사로 Git 서버 호스팅과 프로그래밍 협업을 위한 다양한 기능을 제공하고 있는 서비스

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


### Git bash vs Sourcetree
- git bash는 CLI환경으로 명령어를 사용하여 git을 사용함
- Sourcetree는 다양한 명령어를 GUI로 시각화하여 쉽게 git을 사용하기 위한 도구 

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

### Git 사용 예시
1. Project 선정 및 Clone

2. Git-flow에 따른 사용

3. Conflict가 없으면 브랜치 병합(Merge) 혹은 Pull Request

4. push 권한이 없는 프로젝트라면 Folk후 2~3 반복
------
## SVN

### Visual SVN Server Manager









