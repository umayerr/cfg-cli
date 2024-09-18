# Send file(s) to remote repository from working directory

## Step 1: Add file to the stage area

### Add a single file
```
git add <file>
```

### Add all files from current directory (use ```-all``` or ```-A``` or ```*```)
```
git add --all
```

### Add all files from current directory and its child directories
```
git add .
```

## Step 2: Commit and send file to local repository
```
git commit -m "<comment>"
```

## Step 3: Push file to remote repository
```
git push origin <branch>
```


# Unstage (remove from stage area) file(s) but keep the changes in working directory

## Using ```git restore --staged``` (Recommended for Git 2.23 and newer)

### Unstage a single file
```
git restore --staged <file>
```

### Unstage all files
```
git restore --staged .
```

## Using ```git reset``` (Works in all versions of Git)

### Unstage a single file
```
git reset <file>
```

### Unstage all files
```
git reset
```


# Discard changes in working directory
```
git restore <file>
```


# Undo commit from local repository

## Undo the last commit (back to staging area) and keep changes
```
git reset --soft HEAD~1
```

## Undo the last commit (remove from stage area) and keep changes
```
git reset --mixed HEAD~1
```

## Undo the last commit and discard changes from both the working directory and the staging area
```
git reset --hard HEAD~1
```


# Undo commit from remote repository

## Option 1: Amend the last commit, make the changes and force-push the revised commit

### Step 1: Undo the commit but keep the changes staged
```
git reset --soft HEAD~1
```

### Step 2: Make changes or commit again
For any changes add the file first
```
git add <file>
```
```
git commit -m "<comment>"
```

### Step 3: Force push to overwrite the old commit on the remote
```
git push --force

```

## Option 2: If the commit has been pushed and others may be using the branch, it is better to create a new commit that reverts the previous one
```
git revert <commit-hash>
```
