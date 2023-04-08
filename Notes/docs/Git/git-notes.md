# Branch Basics
- local branches
  - create new
  - checkout
  - create and checkout
  - list
  - delete
  - copy
  - move (rename)

- remote branches
  - create new
  - set upstream
  - list
  - delete

# Branch Merging
- merge branches without conflict
- merge branches after resolving conflicts
- what to check before merging?
- when to merge branches
- what to do after merging?

# Updating
- branch pull
- branch fetch (without updating working directory)
- status of files in git tracking
- adding files to git tracking
- branch push
- set up upstream for pushing to remote repo

# Status
- blank - not added to index
- M - modified
- A - added to index
- D - deleted from index
- R - renamed in index
- C - copied in index
- U - updated but unmerged

# commit without staging
- git commit with -a flog

# How to unmodify a modified file to last commit
- git restore <fileName>

# How to remove a file from staged area to unstaged area
- git restore --staged <fileName>

# How to revert all files back to earlier commit
- create and checkout new branch from earlier commit
- make necessary new changes
- merge branch back to main branch
- delete new branch

# delete it later. I will delete it later