# my-git-notes

- Gitlab, BitBucket, are similar to Github
- Git has GUI 

## Why Git ?
- With Git Developers contribute to the same proeject
- You can revert any changes, made before
- You can solve conflicts. Git show you the changes between 2 project
....

## Words
- **Repository**
- **Branch**
- **Local Repo**
- **Remote Repo** 
- **Commit** (snapshot or checkpoint in your local Repo) 
- **Clone** (to get a copy from local or Remote) 
- **push** (upload local changes to remote)
- **pull** (you get changes from remote repo to local)
- **Pull Request** (Tell other about changes to pull it from local t remote) like admin, who review your changes and either accept your pull or reject it. if accept he will pull your changes from local to remote repo.


##

>`git status` -> to show what file are not in the staging area and modified file

>`git add index.html`|| >`git add *` -> to add file to staging area

>`git commit -m "My Comments about the changes"` -> to commit the changes with comment. (move the change from staging area to local)

>`git branch` -> show me all branch

>`git push RemoteName BranchName` -> to push to remote repo. EX: `git push origin master`

>`git remote -v` -> to show remote names

you created a repo and want to add the team to that repo, so go: repo -> setting -> collaborators 

> `git pull RemoteRepoName` -> get any changes on remote repo

### Configuration File
>`git config -l` -> show all configuration

>`git help config` -> for help

>`git config --global user.email` -> show me the user email

>`git config --global user.email "Ibrahim"` -> to edit the user email

>`git config -l --show-origin` -> from where did you get the config

>`git config --global --unset user.name` || `git config --global user.name ""` to delete the value on the user email 

>`git config --global --edit` -> to edit git config. like adding color and some other infos

## generate public key
we use this to not log in everytime, so we create a public key and set it in the repo
>`ssh-keygen -t rsa -b 4096 -C "ourEmail"`

copy content of ssh_rsa.public file, then go: account setting -> SSH and GPG keys
>`ssh -T git@github.com` -> to make sure you are connented to ssh connection

#### Create repo from Existing project
>`git init`

>`git status`

>`git add index.html`

- create the repo in your account on github, then
copy the command with ssh to clone

>`git push -u origin master` -> -u for pulling first then push, to make sure there is no conflicts with pushing

## pull request

## aliases
>`git config --global alias.sta status` -> to make the sta an alias to status

>`git sta` == `git status`

>`git config --global alias.cm "commit -m"`

>`git cm ` == `git commit -m `

- search on google for "git alias list" for good stuffs

## Branches
> `git branch` -> show all branches

> `git branch branchName` -> create a new branch 

> `git checkout branchName` -> to enter a branch

>`git branch -d branchName` -> delete a branch

-d -> save + delete ???

-D -> force delete

> `git checkout -b branchName` -> create a branch and enter it

> `git branch branchName;git branch -m newBranchName` -> enter the branch and then rename it to newBranchName

> `git chechout branchName;git merge anotherBranchName` -> to merge a branch with a branch (make both branches as one branch)????


## Stash
to add files to a stash, first move the files to the stage then add them

>`git add file.txt;git stash` ->add file to stage then save files in the stash of git

>`git stash list` -> show me all stashes

>`git stash pop` -> get the lastest stash to my current file

>`git stash save "Text Description to the stash"` -> add a description to the stash

>`git stash apply` -> save changes to the lastest stash

>`git stash pop stash@{2}` -> get a specific stash to current folder

>`git stash drop` -> delete the lastest stash

>`git stash drop stash@{1}` -> delete a specific stash

>`git stash show stash@{2}` -> show stash contents

>`git stash clear` -> delete all stashes

task: create a stash and add files to the stash then create brand and add all file in it from the stash


## Restore and clean

>`git add file.txt` -> move file to staged area

>`git restore --staged file.txt` -> remove file from staged area

>`git clean -n` -> show me what files I am gonna remove with remove command. this command will remove the unstaged file, so if you want not to remove the any file, add this file to the staged area.

>`git clean -f` -> remove all files in the unstaged area
Note: you can do that with GUI in the Studio code 


## Resetting the head
head is the pointer that refer to the last comment, you create
each comment has a hash and to remove a comment you need set the hash in the head to remove everything before 

>`git log` -> show logs

>`git reset --hard hashComment` -> remove every comment before this hash


## Ingnore files and directory
first create `.gitignore` file and write anything inside to be ignored and not uploaded to github

>`code .gitignore` -> open a file 
```
*.log
!vip.log
```
ignore all file with .log and setting ! before a file means, make exception for that file.

>`git add IgnoredFile.txt -f` -> with -force you can add files to the staged area even if the file is ignored.

- search also for "git ignore patterns"

## Tagging and Releasing
after creating your project and pushing it into github, we create tags

>`git tag` -> show all available tags

>`git tag v1.0` -> create tag with name v1.0. comment will be the default

>`git push origin v1.0` -> push the project in the tag v1.0

>`git tag v1.0 -m "Your Comment"` -> create tag with name v1.0 and add new comment

>`git tag -l "v1.*"` -> show all tag name, that begin with `v1.`



# Resource:
https://www.youtube.com/playlist?list=PLDoPjvoNmBAw4eOj58MZPakHjaO3frVMF


