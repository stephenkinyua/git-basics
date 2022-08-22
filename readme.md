# Git Basics

Learning git and github step by step
Git
: Version Control System

#### Making Commits

`git add filename` => add a file to staging area \
`git add .` => add all files in the directory to the staging area

#### Branches

Branches
: Some type of a bookmark in a book | The point which the branch is at | Reference to a certain commit
HEAD
: Pointer to the current location that we are viewing at the moment. We cannot be at 2 points at the same time | Reference to a branch pointer \
Tip
: Last commit in the branch

##### Commands

`git branch` => List branches \
`git branch branch-name` => Create a new branch based upon the current HEAD and give it a branch name \
`git checkout -b branch-name` => Create a branch and switch to the branch immediately \
`git switch -c branch-name` => Create a branch and switch to the branch immediately

##### Switching Between Branches

`git checkout branch-name` => Switch to a branch \
`git switch branch-name` => Switch to a branch

##### Deleting Branches

`git branch --delete` => Delete a branch
`git branch -d branch-name` => Delete a branch (shorthand)
`git branch -D branch-name` => Delete a branch

##### Rename a Branch

1. Change to the branch we want to rename
2. `git branch -m new-name` => Rename a branch

##### Git Diff

Show changes between files between commits or the difference between files in the staging area and the working directory

- Show all unstaged changes

```bash
git diff
```

- List all changes in the working tree since your last commit including staged and unstaged changes

```bash
git diff HEAD
```

- Show only staged changes. Difference btw the last commit and the files in the staging area

```bash
git diff --staged or
git diff --cached
```

###### Git Diff: Narrow down to one file

```bash
git diff --staged example.txt filename.txt
```
