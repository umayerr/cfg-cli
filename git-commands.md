# Linking local machine to remote repository
### Option 1 - Clone remote repository to local machine
```
git clone <remote>
```
### Option 2 - Initialize git in local machine and then link to remote repository
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
<br><br>




# Pushing file to remote repository from local machine
### NOTE: Check status after each step to see how things are changed
```
git status
```
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
### NOTE: Add and commit (Step 1 and 2) in single command
```
git commit -a -m "<comment>"
```
<br><br>




# Commits that are not pushed yet
To see the list of files are committed but not pushed yet:
```
git diff --stat --cached origin/<branch>
```
Or
```
git diff --stat --staged origin/<branch>
```
To see the list of commits that are not pushed yet:
```
git log origin/main..HEAD
```
<br><br>




# Check the git log and find commit hash
To see detail log:
```
git log
```
To see shortcut log:
```
git log --oneline
```
<br><br>




# Check differences between two files
To see the differences between working directory and staged/committed file:
```
git diff
```
To see the changes of a specific commit:
```
git show <commit-hash>
```
To see the differences between two commits:
```
git diff <commit-hash-1> <commit-hash-2>
```
<br><br>




# Unstage file but keep the changes in working directory
### Option 1 - Using ```git restore --staged``` (Recommended for Git 2.23 and newer)
To unstage a single file:
```
git restore --staged <file-name>
```
To unstage all files:
```
git restore --staged .
```
### Option 2 - Using ```git reset``` (Works in all versions of Git)
To unstage a single file:
```
git reset <file-name>
```
To unstage all files:
```
git reset
```
<br><br>




# Discard changes in working directory
```
git restore <file>
```
<br><br>




# Undo commit from local repository
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
<br><br>




# Undo commit from remote repository
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
<br><br>




# Get latest changes from remote repository to working directory
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
<br><br>




# Branch operation (create, merge, delete)
To create a branch:
```
git branch <branch-name>
```
To see all local branches:
```
git branch
```
To see all remote branches:
```
git branch -r
```
To see all local and remote branches:
```
git branch -r -v
```
To see all remote branches with latest commit:
```
git branch -a
```
To switch to new branch:
```
git checkout <branch-name>
```
To check the difference between two branches:
```
git diff <branch-name-1> <branch-name-2>
```
To merge one branch into another, first switch to the branch that will receive the changes:
```
git merge <branch-name>
```
To delete a branch from local repository:
```
git branch -d <branch-name>
```
To delete a branch forcefully from local repository:
```
git branch -D <branch-name>
```
To delete a branch from remote repository:
```
git push origin --d <branch-name>
```
<br><br>




# Delete a file
```
git rm <file-name>
```
<br><br>




# Other useful commands
Check git version
```
git --version
```
To track who modified each line of a file
```
git blame <file-name>
```
To search for text in the repository:
```
git grep <text>
```
To display the commit history along with commit message, author, date, and impacted files:
```
git whatchanged
```
For graphical view:
```
gitk --all
```

