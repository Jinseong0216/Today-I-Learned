# **07/12(금) 수업내용 정리**

- 오늘 할 내용
    - pull(이미 local에 있을 때)
    - clone(local에 없을 때)
    - remote repository
    - How to roll-back


## 원격 저장소
- 코드와 버전 관리 이력을 온라인 상의 특정 위치에 저장하여

    여러 개발자가 협업하고 코드를 공유할 수 있는 저장 공간

    원격 저장소 종류: **GitLab**(SSAFY에서 주로 사용), **GitHub**(Major), **Bitbucket**(Minor)


- **원격 저장소 만들기**
1. GitHub가입(repository를 main말고 master로 변경)
2. create repository
3. 로컬 저장소에 원격 저장소 추가
    - `git remote add origin remote_repo_url`
    - origin(추가하는 원격저장소 별칭)(일종의 convention)
    - remote_repo_url(원격 저장소 주소)
- **주의사항** 
    - terminal에서 Ctrl v 사용하지말고 shift insert 사용하기
    - add commit push 순서 항상 기억하기
    - 원격 repository에도 사실 .git폴더가 있어서 돌아가는 것임을 기억
- `git remote -v`
    - fetch 어디서 가지고 올것인가 의미
    - merge를 한번에 해주는 것이 
    - push(로컬 to 원격)
    - pull/clone(원격 to 로컬)
- `git push origin master`
    - 원격 저장소에 commit 목록을 업로드
    - git에게 origin이라는 이름의 원격 저장소에 master라는 이름으로 올려줘라는 의미
    - 입력하면 인증관리 창이 나옴(처음이라)
    - 권한 인증하면 됨
    - 이제 다시 내 github repository에 들어가면 
        기존에 commit했던 파일들이 올라가있는 것을 확인 할 수 있다.
    - GitHub에서 내용을 확인해보면 어떤 것들이 변경되었는지 알 수 있음.
        (코드 들어가서 보면 색,+기호 ... etc로 확인가능)

- **pull & clone**
    - `git pull origin master`
        -원격 저장소의 변경사항만을 받아옴
        - 이미 clone으로 받아온 경우, 사용하면 편함
    - `git clone remote_repo_url`
        - 원격 저장소 전체를 복제(다운로드)
        - 처음 repository를 받아오는 경우
        - clone으로 받은 프로젝트는 이미 git init이 되어 있음
        - **내가 git으로 관리되고 있는 디렉토리에 git clone해버리면 안됨**
            - git init 두 번 해버리는 것과 같음(원격 repo에도 .git이 있으므로)
        - desktop에서 git clone을 해버리면 first-repo폴더가 생김을 알 수 있음
            - git log로 확인해보면 이전의 변경사항들이 다 나옴을 알 수 있음 
    - `mv -f 기존이름 변경이름`
        - 폴더명 변경
    - 내 GitHub repository를 상대방과 공유하기 위해서는 아래의 내용이 전제되어야 함
        1. repository url을 상대방에게 제공
        2. 상대방의 email을 이용하여 초대 보내기
        3. 상대방의 승인
    - gitignore
        - Git에서 특정 파일이나 디렉토리를 추적하기 않기 위해 사용
        - 한번에 여러 파일이나 디렉토리를 처리할 수 있음
        - `touch .gitignore` 하면 됨
        - `.gitignore` 이름으로 만들어야함.
            - 얘는 확장자가 없음
            - **git init 하기전에 미리 만들어야함!**
                
                방법은 있는데.. 귀찮고 권장하지 않음

                (git rm--cashed 같은 방법을 써야함)
            - gitignore 목록 생성 서비스
                - https://www.toptal.com/developers/gitignore/ 추천
                - Ex) Windows, Mac, Python를 쳐보면 알 수 있음
                - 나오는 내용을 전부 복사해서 .gitignore 파일에 넣으면 됨

- **TIL(Today I Learned)**        

