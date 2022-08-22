# Git Basics

Learning git and github step by step \
Git : Version Control System

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

```bash
git branch -m new-name
```

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

- Show changes between branches (Order Matters)

```bash
git diff branch-one..branch-two or
git diff branch-one branch-two
```

- Show changes between commits

```bash
git diff commit..commit
```

###### Git Diff: Narrow down to one file

```bash
git diff --staged example.txt filename.txt
```

##### Git Stash

- Save changes that u are not ready to commit (staged and unstaged) reverting the changes in your working copy

```bash
git stash or
git stash save
```

- Take changes in the stash and re apply them in your current working copy ie continue from where you left off

```bash
git stash pop
```

- Take what is in the stash and apply what is stashed away without removing it from the stash

```bash
git stash apply
```

- List all stashed items

```bash
git stash list
```

- Apply a specific stash

```bash
git stash apply stash@{2}
```

- Drop or delete a specific stash

```bash
git stash drop stash@{2}
```

- Clear the stash

```bash
git stash clear
```
