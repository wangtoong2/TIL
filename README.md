# SSAFY TIL

## 2025/07/16
    VSCODE Extension
        - python
        - python extension
        - markdown all in one    
    
    GIT LOCAL COMMAND
        touch (file)    -> create file

        rm (file)   -> remove file
        rm -rf (folder) -> remove folder
                
        git init    -> make ".git" folder to start git that makes 

        git config --global -l  -> check git user name & email
        git config --global user.name "username"    -> enter your username to identify who modified them, and push to Git
        git config --global user.email "email"      -> enter your email to identify who modified them, and push to Git
        
        git add .   -> the command stages all changes in the current directory and its subdirectories to the staging area ( dot represents the current directory )
        git status  -> check the staging area's working files

        git commit -m "message" -> create a new commit with the staged changes and attaches a commit message describing the changes
        
        git log -> commit history of the current branch

        git commit --amend  -> update the most recent commit by changing its message or adding new staged changes.
            after change, " esc -> :q! " stages force quit without saving, " esc -> :wq! " stages force quit after saving
        
## 2025/07/17
    GITHUB COMMAND
        git remote add (shortcut_name) (git_url)    -> adds a new remote repository to your local GIT project ( allow you to push and pull code from that remote repository)
            shortcut_name commonly uses "origin"
            git_url is the repository's address

        git remote -v   -> shows the list of remote repositories linked to your local project, along with their URLs ( -v stands for "verbose" )

        git push (shortcut_name) (branch)   -> 

        git pull (shortcut_name) (branch)   -> 

        git clone (url)

        Difference of clone and pull
            d
        
        git checkout -b ->

        

