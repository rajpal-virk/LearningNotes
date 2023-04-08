# Git Commands

## Add local folder to GitHub repo
```shell
git init
# create a new file or have atleast 1 file to commit at this point to repo
git add .
git commit -m "First commit"
git branch -M main
git remote add origin <ssh@remote-repo>
git branch -u origin main
git push origin main
```

## Clone GitHub repo to local
```shell
# go to the parent dirctory and run following clone command
git clone <ssh@remote-repo>
```

## Branches
___
### list branches
```shell
git branch --show-current # show current branch 
git branch -l # list all local branches (--list)
git branch -r # list remote tracking branches (--remote)
git branch -a # list all local and remote (tracked) branches (--all)
```

### create new branch
```shell
git branch <newBranchName>
```

### checkout branch
```shell
git checkout <existingBranchName>
git checkout -b <newBranchName> # -b will create new branch and perform checkout
```

### copy branch
- copy branch with config and reflog (reference-logs)
```shell
git branch -c <branchToBeCopiedFrom> <newBranchToBeCopiedTo>
git branch -C <branchToBeCopiedFrom> <existingBranchToBeCopiedTo> # use -C (uppercase) (--copy --force) if copy is being made to an existing branch
```

### move or rename branch
- move or rename with config and reflog
```shell
git branch -m <oldName> <newName> # --move
git branch -M <oldName> <newName> #force move even if new name given already exists (--move --force) 
```


### delete branch
```shell
git branch -d <branchName>
git branch -D <branchName> # force delete even when branch is not merged to other branch
git branch -r -d <remoteBranchName> # deletes the remote branch locally
# Note: if you delete a remote branch locally but still have to use it. 
# you need to set upstream again, commit and push. Once push is done, new remote branch will 
# appear in the list of remote branches
```

## Remote
### add remote repo
```shell
git remote add origin <ssh@your-remote-repo> # add a remote repo to push or pull
git remote add <nameRepoLocally> <ssh@your-or-contributors-remote-repo>
```

### remove remote repo
```shell
git remote remove origin # remove existing remote repo
```


## Updating Repo

### Merge
```shell
# checkout dev branch
# work and update dev branch
# checkout main branch
# merge dev branch to main branch
git merge dev
# usual practice is delete dev branch (branch that is already merged to other branch)
```

### Fetch or Pull
```shell
git checkout <branchName>
git fetch # this ill not update the working directory 
git pull
```


### Commit changes
```shell
git commit -m "typeYourMessageHere"
git commit -a -m "typeYourMessageHere" # -a flag will add the tracked files to commit.
```

### Push
```shell
git push 
git push origin main
# Note: if push is failed due to no upstream then set up upstream first
git push -u origin <remoteBranch>
```

## Files Snapshotting
### Add files
```shell
git add . # to add all files to commit
git add <fileName> # to add a specific file to commit
```

### Files status
```shell
git status # view staged and unstaged changes
git status -s # view short status of staged and unstaged changes
```

### Difference of files
```shell
git diff 
```

## Undoing Changes
### Unstaging a staged file
```shell
# make change to a tracked file
# check its status, you will notice it has modified status
git reset HEAD <fileName>
```


### Unmodify modified changes
```shell
git restore <fileName>
```

### Unstage a staged file
```shell 
git restore --staged <fileName>
git reset # remove all files from staging area
```

### Restore files to earlier commits
```shell
git reset --soft <commitID> # this will reset to earlier commit id but not change working tree or files back to earlier stage 
git reset --soft <commitID> # this will reset working tree and files to earlier stage. May cause loss changes 
```
