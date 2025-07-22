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
        
        (+추가)
        git checkout -b ( 추가할 branch 명 ) -> branch 추가

        * gitignore
        "touch .gitignore"로 파일 생성 후 파일 내부에 staging area로 옮기지 않을 파일명을 명시한다

        git revert ( commit_hash )  -> 특정 commit을 없었던 일로 만든다
            vim editor => esc -> :wq

        git reset -> 특정 commit으로 되돌리기
            git reflog -> 과거 commit 기록들 열람 가능
            git reset --hard HEAD@{Number} -> 해당 번호 이전 작업 상태로 돌아감
            ( reflog 후 나온 번호 값 {Number}에 입력 )

        Staging area에 있는 작업을 working directory로 옮기기 ( git add 취소하기 )
        1. commit이 없는 경우
            git rm --cached ( file_name )
        
        *권장방법
        2. 이전에 했던 commit이 있는 경우
            git restore --staged ( file_name )

        ( git 2.23버전 업데이트 이후 둘 다 가능, but restore 권장 )

## 2025/07/21
    Python
        Value ( 값 )
            - 표현식이 평가된 결과
            - 더 이상 계산되거나 평가될 수 없는 프로그램의 가장 기본적인 데이터 조각
            - ex: 103.14, "안녕하세요", True

        Variable ( 변수 )
            - 변수 할당
            - 변수명 규칙
              - 알파벳, 언더스코어 ( _ ), 숫자로 구성
              - 숫자로 시작할 수 없음
              - 대소문자 구분
              - 특정 키워드는 파이썬의 내부 예약어라 사용 불가
              - 값+타입+주소 정보를 묶은 것을 객체라고 부름
              - 변수는 특정 객체를 가리키는 이름표
                - 변수는 메모리 주소를 가지지 않음

        Type ( 타입 )
            변수나 값이 가질 수 있는 데이터의 종류
            - 값(피연산자), 연산자로 구성
            - ex: 1 + 2 = 3, "나"+"너" = "나너"
            
            Numeric Types ( 숫자형 데이터 )
                크게 정수, 실수 자료형
                - 지수표현 : 'e' 또는 'E' 사용 ( ex: 12e4 -> 120000 )
                
                산술 연산자 ( 가장 기본이 되는 연산 )
                    덧셈, 뺄셈, 곱셈, 나눗셈, 몫 나눗셈, 나머지, 거듭제곱, 음수 부호
            
            Sequence type ( 시퀀스 타입 )
                여러 개의 값들을 순서대로 나열하여 저장하는 자료형 ( 순서가 있는 자료형 )
                대표 시퀀스 타입 : str, list, tuple, range
                    - 가변 시퀀스 : list, dict, set
                    - 불변 시퀀스 : str, tuple, range
                시퀀스 타입의 5가지 공통 특징
                    1. Order( 순서 )
                        값들이 순서대로 저장 ( 정렬 x )
                    2. Indexing ( 인덱싱 )
                        각 값에 고유 번호(인덱스)를 가지고 있으며, 인덱스를 사용하여 특정 위치의 값을 선택하거나 수정할 수 있음
                    3. Slicing ( 슬라이싱 )
                        인덱스 범위를 조절해 전체 데이터 중 원하는 부분만 값을 잘라내서 사용할 수 있음
                    4. Length ( 길이 )
                        len() 함수를 사용하여 저장된 값의 개수(길이)를 구할 수 있음
                    5. Iteration ( 반복 )
                        반복문을 사용하여 각 값을 하나씩 순서대로 꺼내 사용할 수 있음