## Check git version
```
git --version
```


## Check the git log to see changes
To see detail log:
```
git log				[detail log]
```
To see shortcut log:
```
git log --oneline
```


## Delete a file
```
git rm <file>
```


## Clone remote repository to local machine
```
git clone <remote>
```


## Initialize git in local directory and push file in newly created remote
Step 1 - Go to github.com and create a remote repository
Step 2 - Go to the targated working directory using CLI and initialize git
```
git init
```
Step 3 - Check the configuration file [OPTIONAL]
```
git config --list
```
Step 4 - Configure user name and user email and again check the configuration file [OPTIONAL]
```
git config --global user.name "<name>"
git config --global user.email "<email>"
```
Step 5 - Link the working directory to the remote
```
git remote add origin <remote>
```
Step 6 - Verifiy the new remote URL [OPTIONAL]
```
git remote -v 
```


## Get latest changes from remote repository to local machine
Option 1 - To fetch and merge the changes from remote branch into local branch:
```
git pull origin <branch>
```
Option 2 - First fetch the changes to local repository from romote repository, check the changes using ```diff``` command, and then merge it to local branch:
```
git fetch
```
```
diff <branch> origin/<branch>
```
```
git merge
```


## Send file to remote repository from working directory
### Step 1 - Add file to the stage area
To add a single file:
```
git add <file>
```
To add all files from current directory (use ```-all``` or ```-A``` or ```*```):
```
git add --all
```
To add all files from current directory and its child directories:
```
git add .
```
### Step 2 - Commit and send file to local repository
```
git commit -m "<comment>"
```
### Step 3 - Push file to remote repository
```
git push origin <branch>
```
### Add and commit (Step 1 and 2) in single command
```
git commit -a -m "<comment>"
```


## Unstage file but keep the changes in working directory
### Option 1: Using ```git restore --staged``` (Recommended for Git 2.23 and newer)
To unstage a single file:
```
git restore --staged <file>
```
To unstage all files:
```
git restore --staged .
```
### Option 2: Using ```git reset``` (Works in all versions of Git)
To unstage a single file:
```
git reset <file>
```
To unstage all files:
```
git reset
```


## Discard changes in working directory
```
git restore <file>
```


## Undo commit from local repository
Option 1 - To undo the last commit (back to staging area) and to keep changes:
```
git reset --soft HEAD~1
```

Option 2 - To undo the last commit (remove from stage area) and to keep changes:
```
git reset --mixed HEAD~1
```
Option 3 - To undo the last commit and discard changes from both working directory and staging area:
```
git reset --hard HEAD~1
```


## Undo commit from remote repository
### Option 1 - Amend the last commit
Step 1 - To undo the last commit and to keep the changes staged:
```
git reset --soft HEAD~1
```
Step 2 - To make changes or to commit again. If the file is updated, add the file first then commit; otherwise commit:
```
git add <file>
```
```
git commit -m "<comment>"
```
Step 3 - To force push to overwrite the old commit on the remote repository:
```
git push --force

```
### Option 2 - Revert the last commit
```
git revert <commit-hash>
```
After the execution of ```git revert``` command, a new commit that reverses the previous commit is created. To push the revert commit to the remote repository:
```
git push origin <branch>
```


## Check differences in changes
To see the differences between working directory and staged/commited file:
```
git diff
```
To see the changes of a specific commit
```
git show <commit>
```
To see the differences between two commits
```
git diff <commit1> <commit2>
```


## Check what files are commited but not pushed to remote
## Changing in file after commit (not pushed)
