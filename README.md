# Git Cheat Sheet

## First-Time Git Setup
### Your Identity
```
$ git config --global user.name "mmix-el"  
$ git config --global user.email mmix-el@yandex.ru
```
### Your Editor
```
$ git config --global core.editor vim
```
### Your default branch name
```
$ git config --global init.defaultBranch main
```
### Checking Your Settings
```
$ git config --list
```
## SSH keypair setup for GitHub

### Generate a SSH key pair (private/public):
```
$ ssh-keygen -t ed25519 -C "mmix-el@yandex.ru"
```
OR 
```
$ ssh-keygen -t rsa -b 4096 -C "mmix-el@yandex.ru"
```

### Start the ssh-agent in the background.
```
$ eval "$(ssh-agent -s)"
> Agent pid 59566
```
### Add your SSH private key to the ssh-agent.
```
$ ssh-add ~/.ssh/id_ed25519
```

## Initializing a Repository
### Create a new repository on the command line
```
$ echo $reponame >> README.md  
$ git init  
$ git add README.md  
$ git commit -m "first commit"  
$ git branch -M main  
$ git remote add origin git@github.com:mmix-el/$reponame.git  
$ git push -u origin main  
```
### Push an existing repository
```
$ git remote add origin git@github.com:mmix-el/$reponame.git  
$ git branch -M main  
$ git push -u origin main
```
# Recording Changes to the Repository
## Checking the Status of Your Files
```
$ git status -s
```
## Viewing Your Staged and Unstaged Changes
```
$ git diff --staged
```
## Committing Your Changes
```
$ git commit -m "fix benchmarks for speed"
```
## Removing Last Commit From Local & Remote  
```
$ git reset --hard HEAD~n OR git reset –-hard commit-id  
$ git push -f
```
# Viewing the Commit History
```
$ git log --pretty=oneline  
$ git log --oneline
```
# Limiting Log Output
```
$ git log --since=2.weeks
```
# Working with Remotes
## Showing Your Remotes
```
$ git remote -v
```
## Adding Remote Repositories
```
$ git remote add <remote> <url>
```
## Fetching and Pulling from Your Remotes
```
$ git fetch <remote>
```
## Pushing to Your Remotes
```
$ git push origin main
$ git push -u origin develop  
```
## Inspecting a Remote
```
$ git remote show <remote>
```
## Renaming and Removing Remotes
```
$ git remote rename <old-remote> <new-remote>  
$ git remote remove <remote>
```
# Git Branching

## Creating a New Branch
```
$ git branch testing
```
## Switching Branches
```
$ git checkout -b hotfix
```
## Basic Merging
```
$ git checkout main  
$ git merge hotfix   
$ git mergetool  
```
## Branch Management
```
$ git branch -v
```
## Changing a branch name
```
$ git branch --move bad-branch-name corrected-branch-name  
$ git push --set-upstream origin corrected-branch-name  
$ git branch --all  
$ git push origin --delete bad-branch-name  
```

