GIT COMMANDS
============

# Basics

## List git settings

> `git config --list`

> `git config --global --list`

## User info config

>`git config --global user.name "Diego Lozada"`

>`git config --global user.email "dlozada77@gmail.com"`

## Editor config (Visual Studio Code as Text editor for this training)

> `git config --global core.editor code`

## Enable external text editor, and wait until write down something

>`git config --global core.editor "code -w"`

>`git config --global -e`

## Diff tool MAC P4Merge

> `git config --global diff.tool p4merge`

> `git config --global difftool.p4merge.path "/Aplications/p4merge.app/Contents/MacOS/p4merge"`

> `git config --global difftool.prompt false`

## Merge tool MAC P4Merge

>`git config --global merge.tool p4merge`

>`git config --global mergetool.p4merge.path "/Aplications/p4merge.app/Contents/MacOS/p4merge"`

>`git config --global mergetool.prompt false`

## Diff tool LINUX meld

>`git config --global diff.tool meld`
>`git config --global difftool.meld.path "/usr/bin/meld"`
>`git config --global difftool.prompt false`

## Merge tool LINUX meld

>`git config --global merge.tool meld`
>`git config --global mergetool.meld.path "/usr/bin/meld"`
>`git config --global mergetool.prompt false`

## Create a local repository

>`git init <project_name>`

>`git init .` *git initialize  an empty repository*

## Basic workflow

### Git states
#### Local Git States

> **`Working Directory`** => **`Stating Area`** => **`Repository`** (.git Folder)

#### *1 Working* Directory
Contains all the files and folders for your application which may or may not be managed by Git; either way; git is aware of those files.

#### *2 Staging Area*

The staging area is used to prepare for the next commit. FIles are moved from the modified working directory state to the Git staging area.

>`git add .`  *Add all changes to the git staging area(.)*

>`git add <file_name>` *Add a specific file*

#### *3 Repository (.git folder)*

Contains all the committed or saved changes to Git repository.

**-m** Parameter tells Git to type a message

>`git commit` *Open core editorm you can type a commit message*

>`git commit -m "Message"` *To provide a commit message inline on the command prompt*

##### Express commit 
Doesn't use *`git add`* command

**-a** Parameter tells Git to first add modifed files to the git staging area

>`git commit -am "Message"` *Don't need `git add` command before*


#### *4 Remote Repository*

Save changes on a server

## Checking Repository and Files

### Repository status

Shows not staged and untracked files.

>`git status`

### List all the commits that part of the repository

Uses SHA-1 as commit identifier (commit id).

>`git log`

>`git log --oneline --graph --decore --all`

### Show the last commit and a diff containing

>`git show`
	
### List what files Git is tracking

>`git ls-files`

## Backing Out

Restore a staging file

>`git reset HEAD <file_name>`

After

>`git checkout -- <file_name>`

## Create custom git commands

The new command's name is **"`hist`"** for "`log --online --graph --decorate --all`"

>`git config --global alias.hist "log --oneline --graph --decorate --all"`

After you can use

>`git hist` 

>`git hist <file_name>` 

>`git hist -- <file_name>` 

## Renaming and Deliting files

### Rename File

>`git mv <file_name> <new_file_name>`

>`git commit -m "Renaming message"`

### Delete File

>`git rm <file_name>`

>`git commit -m "Deleting message"` 


### Bash delete (remane file)

>`mv <file_name> <new_file_name>`

>`git add -u` ***-u** (update) to recognize changes*

>`git add -A`

>`git commit -m "Message"`

## Excluding unwanted files from Git

>`touch .gitignore`

>`Write inside ignore files`

>`git add .gitignore`

# Advanced

## Comparing Changes (git diff / difftool)

Cli

>`git diff <id_commit_hash_number>`

>`git diff <id_commit_hash_number> HEAD`

With external tool

>`git difftool <id_commit_hash_number>`

>`git difftool <id_commit_hash_number> HEAD`

# Branches

A branch is just a timeline of commits, braches are the names or labels we give timelines in Git. We can create and delete branches without affecting timelines.

## Types of branches

- ### **Fast-Forward merge**
This happens in the simplest of cases, when no additional work has been detected on the parent branch, or in our case master.Git will simply apply all commits from the other branch directly onto the parent branch, as if we never branched off to begin with. We can disable the fast-forward merges if they are undesired for some reason.

    - Simple Case
    - Like Never Branched (Commits on Destination)
    - Can Be Disabled

- ### ***Automatic***
This happens when Git detects non-conflicting changes in the parent brach Git is able to automatically resolve any conflicts. The old branch's timeline is perserved, and a new merge commit is created to show the merging of the two branches.

    - Non-Conflicting Merge Detected
    - Perserves both Timelines
    - Merge Commit on Destination

- ### ***Manual***
 This happens when Git is unable to automatically resolve any conflicts. Git enters a special conflicting merge state, wich means that all merge conflicts must be resolved prior to moving forward witah a commit.

     - Automatic merge not possible
     - Conflicting merge state
     - Changes saved in Merge Commit

# Special Markers

Git has special markers or pointers. One popular marker is called **HEAD**

- ### ***HEAD***
Is normally the last commit of the current branch, that means tath, as we switch branches, the location of HEAD moves to match commit location of that branch.

    - Point to last commit of current branch
    - Can be moved (Advanced)

# Branches

> `git branch` *shows the current branch*

> `git branch -a` *list all of the branches*

> `git checkout -b <branch_name>` *To create new branch*

> `git diff <branch_name> master` *To show differences between a branch regarding to master branch*

> `git checkout <branch_name>` *To switch to anothe branch

TO merge into another branch (fast-forward):

Go to destination branch: 

> `git checkout <destination_branch_name>`

After

> `git merge <source_branch_name>`

Delete branch

> `git branch -d <branch_name>`

# Conflict Resolutions

> `git mergetool`

Add ".orig" files to .gitignore

# Tagging

Create

> `git tag <tag_name>`

List
> `git tag --list`

Delete

> `git tag -d <tag-name>`

Example:

> `git tag -a v1.0 -m "Release 1.0"`

> `git tag --list`

> `git show v1.0`

# Stashing (Save temporary changes)

After modifying some file

> `git stash`

> `git stash list`

> `git stash pop` *Undoes `git add` and `git commit` (changes back) from the stage list*

> `git stash clear`

# Time Travel (Reset, Reflog)

- **soft reset**.- least destructive
Git perserves Staging area

> `git reset <id_commit> soft` 

> `git reset <id_commit> --mixed` *default*

> `git reset <id_commit> --hard` 

Reflog (TODO)

> `git reset --hard <id_number>`

# Going Remote


Clone a repo (previouly you need add a ssh key)

>`git clone git@github.com:kaskasmeister/training.git`

## Manage remote repositories

> `git remote remote -v`
