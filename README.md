This document lists some of the common commands used for `Git`.

# Cheat Sheet
- [Cheat Sheet](#cheat-sheet)
  * [Commands](#commands)
    + [History](#history)
      - [Detailed](#detailed)
      - [Short](#short)
    + [Clone](#clone)
      - [Https](#https)
      - [SSH](#ssh)
      - [Single branch](#single-branch)
    + [Config](#config)
      - [Local](#local)
      - [Global](#global)
      - [Alias](#alias)
    + [Status](#status)
    + [Add](#add)
    + [Commit](#commit)
      - [Undo](#undo)
      - [Commit](#commit-1)
    + [Checkout](#checkout)
    + [Stash](#stash)
    + [Push](#push)
    + [Pull](#pull)
  * [References](#references)

## Commands

### History 

#### Detailed

```sh

git log

```

#### Short

```sh

git shortlog

```

```sh

git log --oneline --no-merges

```

### Clone

#### Https

```sh
git clone https://github.com/ashwanikumar04/git-cheatsheet.git
```

#### SSH

```sh
git clone git@github.com:ashwanikumar04/git-cheatsheet.git

```
#### Single branch
Sometimes when the repository is very large, we only want to clone a single branch. Use below command to clone a single branch
```sh
git clone git@github.com:ashwanikumar04/git-cheatsheet.git -b master --single-branch

```

### Config

The following command makes the output of git commands colorful.
```sh
git config --global color.ui true
```

#### Local

```sh
git config user.name "Ashwani Kumar"
git config user.email "ashwanikumar@test.com"
```

#### Global


```sh
git config --global user.name "Ashwani Kumar"
git config --global user.email "ashwanikumar@test.com"
```

#### Alias

```sh
git config --global alias.st status
```
Just type `git st` whenever we want to see the status of the repository


```sh
git config --global alias.co checkout
```
Just type `git co` whenever we want to check out a branch


```sh
git config --global alias.st status
```
Just type `git ci` whenever we want run a commit

### Status

`git status` Shows the status with tracked and un-tracked files

### Add

```git add .``` Adds all the files in the current directory to staging.

```git add -A``` Adds all files in the current repository (even new files that are not yet tracked)

```git add -u```  Add all files that are already being tracked (ignore new files)

### Commit

#### Undo

`git reset --soft HEAD^` Undo last commit of entire repo, but leave files staged.

`git reset --hard HEAD^` Completely blow away last commit. Changes files to state of previous commit.

`git reset --hard HEAD^^` Completely blow away last two commits. Changes files to state of previous commit.

`git reset --hard HEAD^^^` Completely blow away last three commits. Changes files to state prior to last third commit.


**Returns files to state they were in, after specified commit**

```sh
git reset --hard <sha-of-commit>

git push origin HEAD --force

```

#### Commit

`git commit -m "Add file to repository"` Commit staged files to the repository

`git commit --amend -m "New Message"` Changes the commit message for the last commit

`git commit -am "New Message"` Lets us add and commit all tracked, modified files in one step.

### Checkout

`git checkout -b <name_of_branch>` Create a branch and check it out in one step

`git branch <name_of_branch>` Create a branch, but stay in current branch.

`git checkout <name_of_branch>` Check out an already created branch

`git branch` See a list of all branches, highlights the currently checked out branch

`git checkout master` Checkout master branch

`git branch -d <name_of_branch>` Remove branch locally, but only if we have merged branch.

`git branch -D <name_of_branch>` Remove branch even if we haven't merged changes.

### Stash

`git stash` Use this to stash all the changes to the current repository

`git stash apply` Use this to apply the last stash

### Push

`git push --set-upstream origin <branch>`
`git push`

### Pull

`git pull origin/master`


## References

1. [Treehouse](https://github.com/treehouse-dave/get-acquainted-with-git)
