# Git Basics

Learning git and github **step by step** \
Git : Version Control System

## Making Commits

- Add a file to staging area

```bash
git add <filename>
```

- Add all files in the directory to the staging area

```bash
git add .
```

## Branches

**Branches**: Some type of a bookmark in a book | The point which the branch is at | Reference to a certain commit \
**HEAD**: Pointer to the current location that we are viewing at the moment. We cannot be at 2 points at the same time | Reference to a branch pointer \
**Tip**: Last commit in the branch

### Commands

- List all branches

```bash
git branch
```

- Create a new branch based upon the current HEAD and give it a branch name

```bash
git branch <branch-name>
```

- Create a branch and switch to the branch immediately

```bash
git checkout -b <branch-name>
```

- Create a branch and switch to the branch immediately

```bash
git switch -c <branch-name>
```

#### Switching Between Branches

- Switch to a branch

```bash
git checkout branch-name or
git switch <branch-name>
```

#### Deleting Branches

- Delete a branch

```bash
git branch --delete branch-name or
git branch -d branch-name
```

- FORCE Delete a branch

```bash
git branch -D <branch-name>
```

#### Rename a Branch

1. Change to the branch we want to rename

```bash
git branch -m <new-branch-name>
```

## Git Diff

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

#### Git Diff: Narrow down to one file

```bash
git diff --staged example.txt filename.txt
```

## Git Stash

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

## Going Back In Time

- Go back to a specific commit

```bash
git checkout <commit-hash>
```

- Re attach the HEAD by switching to a branch or creating a new branch

```bash
git switch <branchname>
```

### Using HEAD to Go Back in Time

- Checkout parent commit

```bash
git checkout HEAD~1
```

- Checkout grandparent commit

```bash
git checkout HEAD~2
```

- Go back to the previous branch before you switched to the current HEAD

```bash
git swicth -
```

### Discarding Changes on a file with git checkout

- Reset file contents back to when we made a commit (last commit)

```bash
git checkout HEAD filename or
git checkout -- <filename>
```

### Working with git restore

- Reset file contents back to when we made a commit (last commit)

```bash
git restore <filename>
```

- Reset file contents back to a specific commit

```bash
git restore --source HEAD~2 <filename> or
git restore --source <commit-hash> <filename>
```

#### Unstage files with git restore

- Unstage a file

```bash
git restore --staged <filename>
```

### Working with git reset

- Reset the repo back to a specific commit without getting rid of the changes

```bash
git reset <commit-hash>
```

- Reset the repo back to a specific commit while removing the changes on the working directory

```bash
git reset --hard <commit-hash>
```

### Working with git revert

- Revert a change from a commit while keeping the history of the commit. Commonly used when working in a team and the commit has already been pushed. This command **creates** a new commit in the process.

```bash
git revert <commit-hash>
```

## Working with Remote Repositories (GITHUB)

- View any existing remotes for your repo

```bash
git remote -v
```

- Add a new remote

```bash
git remote add <name> <url>
```

- Remove a remote

```bash
git remote remove <name>
```

- Rename a remote

```bash
git remote rename <old> <new>
```

- Push a repository to remote

```bash
git push <remote-name> <branch>
```

### Remote Tracking Branches

A reference to the state of the branch on the remote.

- View remote branches

```bash
git branch -r
```

- Pull a remote branch by creating a branch locally named exactly the same as the remote branch. By doing this, git sets up the local branch to track the remote branch automatically

```bash
git checkout <branch-name> or
git switch <branch-name>
```

### git fetch

- Take changes from the remote repository to the local repository (.git) and NOT into the working directory. These changes are not integrated into our working files. Download changes without integrating them.

```bash
git fetch or
git fetch origin <branch-name>
```

### git pull

- Take changes from the remote repository to the local repository (.git) and **merge** them into the current branch or working directory.

```bash
git pull
```

### git rebase

Give my branch a new base at the tip of the branch I am merging to.
Example: merge feature onto master

```bash
git swicth feature
git rebase master
```

### interactive rebase

Interactive rebase has a number of options and can be used to:

1. delete coomits
2. join together a number of commits
3. reword the commit message

- Go back 3 commits and rewrite history

```bash
git rebase -i HEAD~3
```

## Working with Git Tags

Label pointing to a particular commit (moment in time). \
Think of it as a sticky note on a commit marking important moments in the history of the repository. \
It is commonly used to mark releases. ie When code is merged onto the master branch we have a new release.

### Types of Tags

1. Light Weight Tags - just a label that points to a commit
2. Annotated Tags - a label with extra metadata

### Tag Commands

- List all tags in the current repository

```bash
git tag or
git tag -l
```

- Filter the tags according to a certain pattern

```bash
git tag -l "*beta*" or
git tag -l "v4*"
```

- Checkout a Tag

```bash
git checkout <tag>
```

- Compare two tags with the diff command

```bash
git diff <tag-one> <tag-two>
```

#### Lightweight Tags

- Create a lightweight tag

```bash
git tag <tag-name> or
git tag <tag-name> <commit-hash>
```

#### Annotated Tags

- Create an annotated tag

```bash
git tag -a <tag-name> or
git tag -a <tag-name> <commit-hash>
```

- Show the metadata for the anotated tag

```bash
git show <tag-name>
```

#### Modifying Tags

- Change the commit that a tag points to by using the (-f | --force) flag

```bash
git tag <tag-name> <commit-hash> -f
```

#### 🚨 Deleting Tags

- Delete a tag

```bash
git tag -d <tag-name>
```

#### Pushing Tags to a remote

- Push a single tag

```bash
git push origin <tag-name>
```

- Push all tags

```bash
git push origin --tags
```
