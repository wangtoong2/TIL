# SSAFY TIL

## 2025/07/16
    VSCODE Extension
        - python
        - python extension
        - markdown all in one    
    
    GIT LOCAL COMMAND
        touch (file)    -> 파일 생성 ( create file )

        rm (file)   -> 파일 제거 ( remove file )
        rm -rf (folder) -> 폴더 제거 ( remove folder )
                
        git init    -> GIT 시작
        ( It initializes a new Git repository in the current directory. creates a  hidden .git folder that tracks version history )

        git config --global -l  -> 사용자 확인 ( check git user name & email )
        git config --global user.name "username"    -> 이름 입력
        ( enter your username to identify who modified them, and push to Git )
        git config --global user.email "email"      -> 이메일 입력
        ( enter your email to identify who modified them, and push to Git )
        ( 제어판 -> 사용자 계정 -> window 자격 증명 -> github, gitlab 제거 ) -> 타인의 계정이 접속되어 있을 경우 내 계정 로그인 시 필요

        git add .   -> 폴더 전체 Staging area에 추가, .이 전체라는 의미 지님
        (the command stages all changes in the current directory and its subdirectories to the staging area ( dot represents the current directory ))
        git status  -> Staging area의 작업 파일 확인
        ( It checks the staging area's working files )

        git commit -m "message" -> Commit. repository에 업로드
        ( It creates a new commit with the staged changes and attaches a commit message describing the changes )
        
        git log -> 이력 확인 ( commit history of the current branch )

        git commit --amend  -> vim editor에서 commit message 수정
        ( It updates the most recent commit by changing its message or adding new staged changes. )
            vim editor에서 수정후
                저장하지 않고 강제종료 esc -> :q!
                저장하고 강제종료 esc -> :wq!
            after change, " esc -> :q! " stages force quit without saving, " esc -> :wq! " stages force quit after saving
        
## 2025/07/17
    GITHUB COMMAND
        git remote add (shortcut_name) (git_url)    -> 로컬 저장소와 원격 저장소를 연결
        ( It adds a new remote repository to your local GIT project ( allow you to push and pull code from that remote repository))
            shortcut_name commonly uses "origin"
            git_url is the repository's address

        git remote -v   -> remote 목록 확인
        ( It shows the list of remote repositories linked to your local project, along with their URLs ( -v stands for "verbose" ))

        git push (shortcut_name) (branch)   -> 가장 최근에 commit 되어있던 것 push ( +는 강제로 push함을 의미 )
        ( It uploads local commits to a remote repository. Typically used after "git commit" )

        git pull (shortcut_name) (branch)   -> 원격 저장소의 브랜치 변경사항을 로컬로 가져와 병합함
        ( It fetches changes from a remote repository and merges them into your current branch )

        git clone (url) -> 해당 github 저장소를 내 컴퓨터에 복제함
        ( copies a remote Git repository to your local machine )

            Difference of clone and pull
                처음 받을때는 clone -> 업데이트 사항이 있을때 pull
                .git 폴더가 없으면 pull을 받을 수 없음 ( 새로운 작업환경에서 clone 이용 )
                Use "git clone" when you don't have the repository yet
                Use "git pull" when you already cloned it and want to update it with the lastest changes.

            Clone을 받으면 Remote를 할 필요가 있을까?
                remote를 할 필요가 없다.
                  git clone을 실행하면 git은 자동으로 다음을 설정함
                  1. 원격 저장소를 "origin" 이라는 이름으로 등록
                  2. 로컬 브랜치를 원격 브랜치와 연결
                  3. 이후 "git pull", "git push" 등을 별도 remote 설정 없이 바로 사용 가능
                  => "git clone" = "git init" + "git remote add origin ..." + 초기 fetch(변경사항 가져오기, 자동 병합은 X)
        
        git checkout -b ->

        

