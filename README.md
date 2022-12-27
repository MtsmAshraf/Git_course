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
        NOTE: after modifing an added file u do have to add it again to the stage

        - git branch: to get the branch name

        - git remote -v: to get the remote name
        NOTE: u can see the file path like this (C:\Users\Moatasim\Downloads\My-Github\Git_course (main -> origin))
        (main -> origin) => (Branch Name -> remote name)

        - git push *REMOTE* *BRANCH*: to push to remote that we cloned the repo from

        - git repo *REMOTE*: to pull files from the centralized server to local

        - on github: if someone who is NOT a team member wanted to make a change in the files he takes a fork from the file then requeats to add it to the repo and the repo owner accpets or refuse

        if he is a team member he do not have to make a request he just make the changes

        - git config --list (git config -l): to show the list of all configs
        - git help config: to go to help tab to see more about configs

        - git config --global *configName*: to show configName value
        - git config --global *configName* "*value*": to set configName value
        - git config --global --unset *configName* "*value*": to remove configName


        - git config enables us to edit many configs from user name to coloring in the cmd line
        - this can be done using cmd line using the "git config" commands

        - OR using editor: to open it "git config --global --edit" this opens editor to edit configs using it

        - public key generation:
        - ssh-keygen -t rsa -b 4096 -C "mo32000a@gmail.com"
            "rsa": algorithm type
            "4096": no of bits
        - after typing this command, u can enter a passphrase for this public key

        - cat ~*filePath*: to show the content of a file, so can use it with the public key file path to get the public key from it, then we add it to github

        - to test this:
            - ssh -T git@github.com
            - then the passphrase (if exists) is needed
            - NOW: You've successfully authenticated,

        - PREVIOUSLY we made a repo then cloned its content to our local then edited it then push it again to remote
        so it was automatically connected to remote

        - NEXT: we will do the opposite, we need to push an existing project to a repo

        [USEFUL Commands in this area]:
            - mkdir *name*: make a new directory (folder)
            - git init: make an empty repo in local path
            - touch *name*: make a new file

        - NOW assume we have an empty repo on github and we need to upload our project to it
            - get the command with the ssh link of the repo in it (git remote add origin git@github.com:*userName*/*repoName*.git)
            - then type the command (git push -u origin main)
            - NOTE: the prev command is the same as we did before to push to remote but what is the extra "-u" in it? it means this command will pull then push to so u have the newest changes of the project before pushing the new files

        - Pull Requests: assume there is an app that u need to contribute on it so u take a fork from it and make ur changes in the code files
            - then u need to push these files back to the main app repo. To do such a thing u MUST make a request and the owner of the main repo can accept or deny it

            - on github, after committing the changes in the files (DIRECTLY TO THE MAIN), so far the changes will appear in ur forked (local) repo not in the main repo
            - to make a pull request, go to Pull Request tab in the forked repo nad make a new pull request and write a title and disc for it
            - if there is any conflict in the codem it will appear cuz the site compares changes at this step
            - then that request will be sent to the owner of the main repo so he can accept or deny it

            - the prev is valid if the commit in the forked repo is made DIRECTLY TO THE MAIN, what if is is made to a branch in it?
                - in this case, u need to make a pull request to push files from that branch to the main of the forked repo and the admin can accept or deny it (the admin can be u too)
                - then u can make a pull request to the main repo u forked from

        - Aliases: making the commands shorter to save time
        - use the command : git config --global alias.*ALIAS* *COMMAND*
        - if the COMMAND is a two-word command use double qoutes "*COMMAND*"
            - ex: git cofig --global alias.st status
        - then to use it u can use either the alias: git *ALIAS* or the main command
            - for the prev ex: git st
        - NOTE: (git config --global alias.*ALIAS*) shows (*COMMAND*)

        - There are already-made aliases list online that can be used

        - Branches
        - git branch: show branch
        - git branch *NAME*: create branch called *NAME*
        - git checkout *NAME*: go to branch called *NAME*
        - git checkout -b *NAME*: go to branch called *NAME* and go to it
        - git branch -d *NAME*: delete branch called *NAME* (this command will NOT delete the branch if it is not merged yet)
        - git branch -D *NAME*: delete branch called *NAME* (this command will delete the branch anyway)
        - git branch -m *newNAME*: rename the current branch and call it *newNAME*

        - how can u commit branch?
            - 1st method: merge with main
                - 1. go to main branch
                - 2. merge the needed branch (git merge *NAME*)
                - [OPT] now u can delete the branch
                - 3. push main to remote (git push origin main)

            - 2nd method: push directly from the branch to remote
                - 1. in the branch (git origin *NAME*)
                - now u can delete it
                - 2. now u NEED to go to github and make a pull request for this branch to be added to remote repo

        - Stash: used to stored files that u do NOT want to push now, then u can get it back whever u need
            - git stash: stash (store) files after adding them to stage using "git add ..."
                (NOTE: each stash command after each add command makes a new stash (box) and stashes files in it
                - The new stash will be the stash of id{0} (pushed to the beginning of the stash list))
            - git stash save "*MSG*": to add a MSG with this stash
            - git stash list: to show if there r stored files or not
            - git stash pop: to get the stored files out of the stash list so they can be ready to be committed
                - NOTE: pop drops (deletes) stash after getting the files out of it
            - git stash apply: to get the stored files out of the stash list so they can be ready to be committed
                - NOTE: apply do NOT drops (deletes) stash after getting the files out of it (it is like copying the files of this stash)
            - git stash drop: to drop (delete) a stash
                - NOTE: dropping a stash deletes its content and it can NOT be restored
            - git stash show: to show the content of a stash

            - The prev commands is applyed on the stash@{0} (the latest to be added to the list) by default
                ex:git stash pop => pops the latest , git stash drop => drops on the latest
            - to access a certain stash use stash@{*ID*} after any command
                ex:git stash pop stash@{1} => pops the stash of id{1} (the second in the list) , git stash drop  stash@{1} => drops on the stash of id{1} (the second in the list)

            - git stash clear: to drop (delete) all stashes

            - Restore and Clean
            - git restore --staged *NAME*: to unstage a file that u staged before using "git add ..."
            - git clean -n: just SHOWS what files would be cleaned
            - git clean -f: cleans unstaged files
                - NOTE: since "git clean -f" cleans unstaged files only, u can "use git clean -n" to show what files would be cleaned, so if there is a file that u do NOT want it to be cleaned, u MUST stage it using "git add..." before using git clean -f


            - Reset: to remove commits from the remote repo
            - git log: to show all commits in the repo
            - what is HEAD in git? it is like a pointer points to the latest commit (the most in top)
            - excuting the command "reset" removes all commits above the HEAD
            - so how can we reset (remove commits)?
                1. Move the HEAD to the commit that we need to ramove all commits after it, HOW?
                    - git reset --hard *COMMIT HASH* => *COMMIT HASH* can be found on github OR by the command git log
                    - git push origin main --force: to recommit files so now the unnedded commits are gone
 -->
