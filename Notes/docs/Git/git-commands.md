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