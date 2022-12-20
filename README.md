# Git_course

Repo of git and github course

<!-- Course Comments -->
<!--
    Git
        - is Distributed Version Control System
        - Free and Open Src
        - Github != Git, it is just simplifies using git [also Do GitLab and BitBucket], so u can use git without github
        - Git has GUI

    WHY Git?
    - devs contribute to the same projet
    - u can revert changes
    - u can collaborate to fix issues
    - u can collaborate to create new features
    - u can organize features
    - u can solve conflicts

    Keywords:
        - Repository (repo): it is like a store of a project files
        it is better to have a new one for each new project
        - Branch: Part of a repo (it is better to have a new one for each new feature or enhancement)
        - local repo: a repo on ur computer locally
        - remote repo: a repo online u work on remotely
        - commit: like a spanshot or checkpoint in ur local repo
        - push: upload changes from local to remote
        - pull: pull changes from remote to local
        - pull request: a request to another persom to pull changes from local to remote repo

        - no need to connect to remote repo to work, u can work locally then push later
        - anyone can pull or push depending on permissions

        How can u clone a repo from remote to local?
        1. create repo on github
        2. get its link
        3. in the project folder, use the command line and run the command "git clone *link of the repo*"
        now it should be cloned successfully

        Commands:
        - git status: to show the status after any change

        - git add *file*: to add files to the stage [git add * : adds all files]
        now the files are added to the stage

        - git reset HEAD *file*: to unstage a file
        (NOTE: if u created a file after cloning the repo from remote to local, u HAVE TO add it to the stage using git add command)

        - git commit -m "*description*": to commit added files to local repo
        now the files are committed to the local repo
        NOTE: after modifing an added file u just need to commit it, u do NOT have to add it again to the stage

        - git branch: to get the branch name

        - git remote -v: to get the remote name
        NOTE: u can see the file path like this (C:\Users\Moatasim\Downloads\My-Github\Git_course (main -> origin))
        (main -> origin) => (Branch Name -> remote name)

        - git push *REMOTE* *BRANCH*: to push to remote that we cloned the repo from

 -->
