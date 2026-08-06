# Git tutorial for developers
In this set of documents, we intend to teach the **Git source control** completely and comprehensively, the training starts from the basic level and covers all the commands that are widely used in the git.
- This collection has been prepared and collected by [**M.Taghizadeh**](https://github.com/m-taghizadeh) 
- there is no problem with any use by mentioning the source :)


## Getting Started
- [Git installation](#Git-installation)
- [Git Config](#Git-Config)
- [Git Phases](#Git-Phases)
- [Git Commands](#Git-commands)   


## Git-installation

- **linux**
    <p style="text-align:right">
    برای نصب این نرم افزار بر روی لینوکس های مبتنی بر دبیان مانند ابونتو دستور زیر را در خط فرمان اجرا کنید
    : در هر کدارم از پکیج منیجر های توزیع خود میتوانید به راحتی گیت را نصب کنید ، برای مثال در اوبونتو  به شکل زیر 
    </p>

    ```shell
    >> sudo apt-get update
    >> sudo apt-get install git
    ```

    <p style="text-align:right">
    : در توزیع فدورا با یکی از دو دستور زیر   
    </p>

    ```shell
    >> sudo dnf install git
    یا 
    >> sudo yum install git
    ```

    <p style="text-align:right">
    : در توزیع آرچ لینوکس با پکیج منیجر پکمن  
    </p>

    ```shell
    >> sudo pacman -S git
    ```
<br>

- **mac**
    <p style="text-align:right;">
    راهکارهای گوناگونی برای نصب گیت روی مک وجود دارد اگر پیش از این ایکس کد را نصب کرده باشد (یا ابزار خط فرمان آن را) امکان دارد که گیت به صورت نصب شده روی سیستم او وجود داشته باشد. برای بررسی این موضوع، باید ترمینال را باز و دستور ورژن گیت را وارد کند
    آسان‌ترین راه برای نصب گیت روی مک، استفاده از نصب کننده گیت (دانلود از خود سایت گیت) است، 
    بنابراین یک نسخه از گیت روی مک بوک ها نصب هست ولی برای نصب جدید ترین نسخه میتوانید از پکیج منیجر های محبوب استفاده کنید مانند
    </p>
    brew package manager
<br><br>

- **windows**
    <p style="text-align:right; dir:ltr">
    در ویندوز هم به راحتی میتوانیداز طریق پکیج منیجر های ویندوزی نظیر چاکلتی گیت را نصب کنید ولی روش بهتر از طریق نصب کننده گیت ، گیت را نصب کنید با مراجعه کردن به لینک زیر

    https://git-scm.com/downloads
    </p>
<br><br>

- **Verifty**
    <p style="text-align: right;">
    : در ترمینال خود این دستور را بنویسید ، باید بعد از آن ورژن گیت نصب شده خود را مشاهده کنید 
    </p>
    
    ```shell
    >> git --version
    ```


# Git-Config
- Local level config
- Global level config
- System level config


## Git-Phases

Three phases of git :
1. **Working directory** | **Working tree** | **Working Space** 
2. **Index** | **Stage**
3. **Repository**

Files in a repository go through three stages before being under version control with git:
- **Untracked**: the file exists, but is not part of git's version control
- **Staged**: the file has been added to git's version control but changes have not been committed
- **Committed**: the change has been committed
- git status : is used to understand what stage the files in a repository are at.


## Git-commands
```shell
# Session 04 : Git installation
>> git --version # get git version 

# Session 05 : Git config 
>> git config --global user.username "M Taghizadeh" 
>> git config --global user.email "example@gmail.com" 
>> git config --global --list | -L # get list of gloabl configs 
>> git config --global --edit # --edit for edit git configs
>> git config --local alias.st "status" # add alias for git commands
>> git config --local alias.gloa "log --oneline --all" 

# Session 07 : Create Repository 
>> git init # initial repository
>> git clone <https://example.RepoAddress.com> # clone repository from remote

# Session 09 : Deep dive into the phases of Git
>> git status # show untrackted, modified, staged files
>> git add filename # add untrackted or modified file to stage
>> git add . # add all of untrackted or modified file to stage
>> git add -A # add all of untrackted or modified file to stage
>> git add --patch # add part of file to staging area
>> git commit 
>> git commit -m | --message "comm_msg" # Commit changes of tracked files to head
>> git commit -a -m "comm_msg" # add all changes of tracked files to staging and commit them.
>> git commit --amend # amend commit
>> git commit --amend --no-edit 

# Git Remove file
>> git rm filename

# Session 10 : Git history
>> git log # log of commits with date, descriptions and author Name
>> git log --oneline # summary of git log
>> git log filename #log of commits with date, descrtions and author Name related to a specific file
>> git log -p filename # git log with all diff between commits 
>> git show <commID_10> # show all info + diff HEAD,comm(HEAD-1) 
>> git show <commID_10> filename # show all info + diff commID9,commID10
>> git reflog # git reference log
>> git log --since "2 days ago" #show only commits that occur one day ago until now
>> git log --until "18:21" #only shows commits that have occurred until 18:21
>> git log --author "Mohammad" #only shows the commits that user Mohammad has made
>> git log --since "Sun Nov 29 17:16:01 2020" --oneline #only shows commits that have occurred in specific date and time
>> git log --grep "add" #show all commits that have add in their message
>> git log --stat --summary #show the number of changes per file
>> git log --all --graph #show all commits of all branchs in tree mode 

# Session 11 : Git alias
>> git config --global alias.gs "status" #set shortcuts for git commands for example: gs instead of status
>> git config --global alias.glo "log --oneline"

# Session 12 : Git help
>> git help <any_commands> #show document related to command

# Session 13 : Git add part of a file to the staging phase
>> git add --patch | -p 

# Session 14 : Git diff 
>> git diff <commID_1> <commID_2> filename #show differents between first commit and second commmit in a specific file 
>> git diff --staged filename #show all changes that were staged in a specific file 
>> git diff HEAD #show all changes that were not commited, whether staged or not
>> git diff #show all changes that were not staged 
>> git diff branch1..branch2  #show the differences between branch1 and branch2

# Session 15 : Time travel (git checkout, git restore)
>> git checkout 
>> git checkout -b branch_name commID # checkout in commID and create new branch
>> git checkout -b branch_name tag_name # checkout in tag_version and create new branch 
>> git restore filename
>> git restore index.txt # restore unstaged parts of file to head => see that with "git diff"
>> git restore --staged index.txt # restore staging parts of file to unstaged => see that with "git diff --staged"
>> git restore --source HEAD index.txt # restore staging part of file and unstaging part of file => see that with "git diff head"

# Session 16 : Git reset
>> git reset # by default: --mixed
>> git reset --soft  <commID> # reset commits history  
>> git reset --mixed <commID> # reset commits history and staging area
>> git reset --hard  <commID> # reset commits history and staging area and working directory
>> git reset --hard  HEAD~2 

# Session 17 : Git revert
>> git revert <commitID>

# Compare Reset and Revert

| Feature                      | `git reset`                          | `git revert`                          |
|------------------------------|--------------------------------------|---------------------------------------|
| **Purpose**                  | Move HEAD and modify history         | Create a new commit that undoes changes |
| **History Modification**     | Yes, it rewrites history             | No, it preserves history              |
| **Data Loss Potential**      | Yes, especially with `--hard`       | No, it preserves previous commits      |
| **Use Case**                 | Undo commits, unstage changes        | Safely undo changes in shared repositories |
| **Safe for Collaboration**   | Not safe, can disrupt others' work   | Safe, maintains history for all users |

# Session 18 : Git branching
>> git branch    # list of all local branchs
>> git branch -r # list of all remote branchs
>> git branch -a # list of all branchs (local branchs and remote branchs)
>> git branch -d branch_name   # delete the branch
>> git branch branch_name # create branch
>> git switch branch_name # switch in branchs
>> git switch -c branch_name # create and switch branch
>> git checkout branch_name # switch branch
>> git checkout -b branch_name # create and switch branch
>> git checkout -b branch_name commID # create and switch branch on the special commit 
>> git log --oneline --all --graph # log of all commity history on all of branch and show that in graph

# Session 19 : Git merging
>> git merge
>> git merge branch_name -m "merge message"
>> git log --oneline --all --graph
>> git merge --no-ff branch_name

# Session 20 : Git rebase
>> git rebase master # on branch feature (for example)
>> git checkout master
>> git merge feature

# Session 21 : Git merging conflicts
>> git merge branch_name # we see this message: "both modified" conflict
>> git merge --abort # aborting merge

# Session 22 : Git stash
>> git stash # tmp storage for saving all of changes in your repo (Tracked files and codes and ...)
>> git stash save
>> git stash save "message"
>> git stash save --include-untracked | -u # for Untacked files
>> git stash show stash@{0}
>> git stash show -p stash@{0}
>> git stash pop stash@{0}
>> git stash apply stash@{0}
>> git stash drop stash@{1}
>> git stash clear
>> git stash list # list of stash
>> git stash --patch | -p : stash part of files

# Session 23 : Git cherry-pick
>> git cherry-pick <commitID>

# Session 25 : Git tag
>> git tag # list of tags
>> git tag -l 'v1.4.2.1.*'
>> git tag v1.0.1 # lightweight tag
>> git tag -a v1.0.0 -m 'my version v1.0.0' # annotated tags
>> git tag -s v1.0.0 -m 'my version v1.0.0' # tag by signiture and pgp or gpg key
>> git tag -d v1.0 v2.0 ... # delete tags
>> git show v1.0.0
>> git checkout -b branch_name commID # checkout in commID and create new branch
>> git checkout -b branch_name tag_name # checkout in tag_version and create new branch
>> git checkout <commID>  # transfer temporarily to a specific commit to check the code in that step and to come back use "git switch -"

# Session 26 : Git blame
>> git blame <filename> 
>> git blame <filename> -L 1,10 # line 1 to 10
>> git blame HEAD <filename>
>> git blame <commID> <filename>  
>> git blame <branchName> <filename>

# Session 27 : Binary search in commits (git bisect)
>> git bisect # binary search commits
>> git bisect start
>> git bisect bad
>> git bisect good <commID> # commID from git log of history
>> git bisect reset # get back to the original branch

# Session 29 : Git remote
>> git remote # list of remotes in rempository
>> git remote add remote_name "http://remote_address.com" # add new remote
>> git remote -v # list of remotes  
>> git remote remove remote_name # remove remote
>> git remote rename remote_name # rename remote
>> git remote show remote_name # more info
>> git push remote_name # <exmp : origin> master
>> git push remote_name tag_name 
>> git push remote_name --tags
>> git pull
>> git fetch
```
