# Git commands

## Git version
`git --version`
```bash
> git --version
git version 2.27.0.windows.1
```

## Full config
`git config --list`
```bash
> git config --list
...
user.email=ricardo@example.com
user.name=Ricardo
```

## Set config name
`git config --global user.name`
```bash
> git config --global user.name "User Name"
```

## Set config email
`git config --global user.email`
```bash
> git config --global user.email "user@email.com"
```

## Initialize repository
`git init`
```bash
> git init
Initialized empty Git repository in C:/Example/.git/
```

## Stage all files then commit
`git add`, `git commit`
```bash
> git add .
> git commit -m "Initial commit"
[master (root-commit) b37578c] Initial commit
 2 files changed, 5 insertions(+)
 create mode 100644 .gitignore
 create mode 100644 README.md
 ```

## Log
`git log`
```bash
> git log
commit b37578c460e1121a781800192cd4547b3f331d3f (HEAD -> master)
Author: Ricardo <ricardo@example.com>
Date:   Tue Oct 25 08:38:30 2022 +0200
```


## Stage all files and commit - one command
`git commit -a -m`
```bash
> git commit -a -m "Fix: typo"  
[master bd8dbaa] Fix: typo
 1 file changed, 1 insertion(+), 1 deletion(-)
```

## Check remote repo
`git remote`
```bash
> git remote
OR
> git remote -v
```

## Add remote repo
`git remote add origin`
```bash
> git remote add origin git@github.com:FrontEndNotes/exammple-repo.git
```

## Push changes to remote repo
`git push`
```bash
> git push origin master -u
Enumerating objects: 7, done.
```

## Pull data from remote repo - fetches the data, needs additional merge to merge local and remote (origin) data
`git fetch`
```bash
> git fetch
remote: Enumerating objects: 5, done.
```

## Merge fetch data from origin/master into local master
`git merge`
```bash
> git merge origin/master
Updating bd8dbaa..1aeaf05
Fast-forward
```

## Pull = Fetch + merge at once
`git pull`
```bash
> git pull origin master
remote: Enumerating objects: 5, done.
```

## clone a repo
`git clone`
```bash
> git clone git@github.com:FrontEndNotes/exammple-repo.git
```

## List of current branches
`git branch`
```bash
> git branch
* master
```

## Rename branch
`git branch -M`
```bash
> git branch
* master
> git branch -M main
> git branch
```

## Create new branch
`git branch`
```bash
> git branch awesome
> git branch
  awesome
* master
```

## Delete branch
`git branch -d`
```bash
> git branch -d awesome
Deleted branch awesome (was 9efdd5b).
```

## Create and checkout new branch - 2 step
`git branch` and `git checkout`
```bash
> git branch awesome   
> git checkout awesome
Switched to branch 'awesome'
```

## Create and checkout new branch - 1 step 
`git checkout -b`
```bash
> git checkout -b cool
Switched to branch cool
```

## Merge 'awesome' branch into 'master' branch
`git merge`
```bash
> git merge awesome
```

## Abort merge
`git merge --abort`
```bash
> git merge --abort
```

## Unstage not saved files
`git reset`
```bash
> git reset

```

## Reset - go back to the last commit - mixed mode - keep the files
`git log` and `git reset`
```bash
> git log
Author: Ricardo <ricardo@example.com>
Date:   Tue Oct 25 09:33:24 2022 +0200

    bad commit

commit b8b45fc7b571c17842e00a4a404b08094b2316fc
Merge: dced740 b103de2
Author: Ricardo <ricardo@example.com>
Date:   Tue Oct 25 09:19:50 2022 +0200

    merge: fixed conflict

commit dced740ee90c7cc3fb2d1bdf467ba17af61f1788
> git reset b8b45fc7b571c17842e00a4a404b08094b2316fc
>

```

## HARD Reset - go back to the last commit - delete the files
`git reset --hard`
```bash
> git reset --hard b8b45fc
HEAD is now at b8b45fc merge: fixed conflict
```

## Update message of the last commit
`git commit --amend`
```bash
> git commit --amend -m "better message"
[master de75846] better message
```

## Update last commit - add file to the last commit
`git commit --amend --no-edit`
```bash
> git add .
> git commit --amend --no-edit
[master 8d687e7] better message
```

## Stash changes (modified files) with the additional name "work-in-progress"
`git stash save`
```bash
> git stash save work-in-progress
Saved working directory and index state On master: work-in-progress
```

## List and apply stash changes (by index)
`git stash list`
```bash
> git stash list
stash@{0}: On master: work-in-progress
> git stash apply 0
On branch master
```

## Github Codespaces - Open a github repo in a cloud-based VS Code
- being on a repo page on GitHub, press `[.]` on a keyboard