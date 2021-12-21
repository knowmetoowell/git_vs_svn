# git_vs_svn

## 개요

## 형상 관리 도구 = 버전 관리 도구

- 형상관리는 소스의 변화를 끊임없이 관리하는 것을 말함

- 프로젝트를 진행하면서 소스 코드를 USB나 메일로 주고받는 건 엄청난 낭비 임과 동시에 보안성 위험이 있다.

   그렇기 때문에 프로젝트를 진행 함에 있어 형상 관리 도구를 사용 한다. 

 - 소스를 버전 별로 관리할 수 있어서 개발할 때 실수로 소스를 삭제하거나, 수정하기 이전으로 돌아가야되는 경우 유용하게 사용되는 툴

 - 또한 팀 프로젝트에서도 누가 무엇을 어떻게 수정했는지도 알 수 있기 때문에 코드를 병합하거나 수정된 소스를 추적하는 데에도 쓰임


----------
## Git
---
### Git-hub
- Microsoft의 자회사로 Git 서버 호스팅과 프로그래밍 협업을 위한 다양한 기능을 제공하고 있는 서비스

### Git-hub 계정 보안

- opt
- ssh



### Git-hub 무료 계정 vs Pro 플랜 계정

- Public 저장소에서는 무료 계정과 Pro 플랜 계정의 차이가 거의 없음
- GitHub Actions 사용 시간이 월 2,000분에서 3,000분으로
- GitHub Packages 용량이 500MB에서 2GB로 늘어남
- Private 저장소에서 무료 계정은 다음과 같은 기능을 사용할 수 없음

        Email을 통한 지원
        3,000분/월 GitHub Actions
        2GB GitHub Packages 스토리지
        비공개 저장소에서 고급 기능 이용 가능
         - 풀 리퀘스트 리뷰 강제
         - 다수의 풀리퀘스트 리뷰어 지정 가능
         - 자동 링크 레퍼런스
         - 깃허브 페이지
         - 위키
         - 보호된 브랜치 기능
         - 코드 소유자(Code owners)
         - 저장소 인사이트




### Git-hub Branch vs Fork
https://devrappers.tistory.com/19?category=856233

### Git-hub pull request
https://devrappers.tistory.com/20?category=856233
### Git-hub action
- CI/CD 툴

### git bash vs Sourcetree
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

img
![Git-Flow](https://github.com/knowmetoowell/git_vs_svn/blob/main/img/git-flow.png "Git-flow 도식화")


------
## SVN
-----
### Visual SVN Server Manager









-----
## 한계점
1. 내부 사용 프로그램

        일반적인 배포(realease) 불가 - 초기 설정이 어려움
2. ini파일

        - 다른 환경에서 사용할 때 ini파일의 경로를 코드 내부(ini_Directory.cs)에서 수정해야 함
        - 다른 환경에서 사용할 때 ini파일 내부의 value를 잘 수정해야 함
        
    ```C#
    ini // ini파일을 로드하는 과정에서 코드 내부의 절대경로를 한번 수정해주어야 함
    .Load(@"C:\Users\user\Desktop\FileManager\FileManager\bin\Debug\FileManager.ini", ordered: true);
    ```
    Ref - [ini_Directory.cs](https://github.com/knowmetoowell/FileManager/blob/main/FileManager/ini_directory.cs)

3. 디렉토리별 다른 업무
        
        3.1 확장자 필터 
        - 현재 프로그램은 디렉토리별 확장자 필터 적용이 안되어 있음
        - 모든 디렉토리에 확장자 필터 한 그룹이 적용됨
        
        3.2 하위 폴더 포함 여부
        - 현재 프로그램은 디렉토리별로 하위 폴더 포함 여부를 선택할 수 없음

        3.3 수행할 작업
        - 현재 프로그램은 디렉토리별로 다른 작업을 실행할 수 없음

        위 문제점들 수정 중

-----
## Scenarioes

### Scenario#1 

        초보 개발자인 이상원(26)씨는 지난 날의 log파일들을 직접 삭제하고 있다.
        그 과정이 번거로워 자동화하려고 하는데,,,
--------        



### Scenario#1 Solution ini File
```
[src_dir]


[dest_dir]


[datetime]
0=0일

;오전 00:00시로 지정됩니다.
;datetime = 숫자 + 일 / 달 또는 월 또는 개월 / 년 형식으로 적어주세요 ex) 30일, 1년, 1달, 2개월, 3월 등


[del_dir]
0=C:\Users\user\Desktop\test_dest1-1
;-----------------------------------------------------------------------------------------------
;기준삭제, 기준복사를 할때는 디렉토리 숫자와 standard, datetime 숫자가 동일 해야합니다.
;-----------------------------------------------------------------------------------------------

[standard]
0=생성, 이전

;standard는 (수정, 생성) | (이전, 이후) 순서로 적어 주세요

[extension]
0=txt
;확장자 필터를 쓰지 않으려면 모두 지우기

[subdirectory]
하위폴더=1
;하위폴더 같이 복사 및 삭제: 0 하위폴더 제외: 1

[auto_execution]
수행할 작업=기준삭제
;전체삭제, 전체복사, 기준삭제, 기준복사를 입력하세요 - 기준삭제 하려면 위 "수행할 작업=기준삭제"기입

[absolute_dir]
실행파일위치=C:\Users\user\Desktop\FileManager\FileManager\bin\Debug\FileManager.exe
ini파일위치=C:\Users\user\Desktop\FileManager\FileManager\bin\Debug\FileManager.ini

[task_scheduler]
작업스케줄러등록여부=0
;0 -> 등록, 1 -> 비등록


```
----
### Scenario#2
        영업팀에서 일하고 있는 이상원(26)씨는 파일 정리가 미숙하다.
        모든 파일을 바탕화면에 저장하여 파일을 실수로 지우거나 잘 찾지 못하는 문제가 있다.
        특히 엑셀파일이 너무 많아 최근에 수정했던 파일만 따로 저장하고 싶은데,,,
----
### Scenario#2 Solution ini File
```
[src_dir]
0=C:\Users\user\Desktop

[dest_dir]
0=C:\Users\user\Desktop\엑셀파일모음

[datetime]
0=2일

;datetime = 숫자 + 일 / 달 또는 월 또는 개월 / 년 형식으로 적어주세요 ex) 30일, 1년, 1달, 2개월, 3월 등

[del_dir]

;-----------------------------------------------------------------------------------------------
;기준삭제, 기준복사를 할때는 디렉토리 숫자와 standard, datetime, standard 숫자가 동일 해야합니다.
;-----------------------------------------------------------------------------------------------

[standard]
0=수정, 이후

;standard는 (수정, 생성) | (이전, 이후) 순서로 적어 주세요

[extension]
0=xlsx
1=csv
;확장자 필터를 쓰지 않으려면 모두 지우기

[subdirectory]
하위폴더=1
;하위폴더 같이 복사 및 삭제: 0 하위폴더 제외: 1

[auto_execution]
수행할 작업=기준복사
;전체삭제, 전체복사, 기준삭제, 기준복사를 입력하세요 - 기준삭제 하려면 위 "수행할 작업=기준삭제"기입

[absolute_dir]
실행파일위치=C:\Users\user\Desktop\FileManager\FileManager\bin\Debug\FileManager.exe
ini파일위치=C:\Users\user\Desktop\FileManager\FileManager\bin\Debug\FileManager.ini

[task_scheduler]
작업스케줄러등록여부=1
;0 -> 등록, 1 -> 비등록
```
