Download and Install git from: https://git-scm.com/



## Terms
* **origin**: default name given to remote server name
* **remote**: as in remote server such as github, gitlab, bitbucket
* **master**: name of the main branch. It is the final and working branch. 
* **commit**: commits are the snapshots or the checkpoints of the changes.
* **push**: act of pushing changes
* **pull**: act of pulling changes
* **fetch**: getting a fresh view on all the things that happened in a remote repository wi**thout integrating changes in your files
* **merge**: 
* **pull request** (PR): way of telling the project that the changes you made are  ready to be reviewed
* **fork**: get a copy of the project for additing more features or for your own use -> make changes and then send a PR
* **stash**: keeps your changes aside while you pull-in recent changes from remote
* **checkout**: When you want to restore a historic version of a specific file.  Thereby, you can reset single files to earlier revisions - while keeping the rest of the project untouched
* **HEAD** is a special pointer that tells git on which brach we are on. It points to a branch and not to a commit. 
* **Working tree** is what we see in our filesystem. Adding, deleting and editing files happens in the working directory.
* **Staging area (index)** Only the files in staging area are snapshotted for the next commit. `git add filename` will start tracking the file from working tree.
## Actual Scenarios

A. Pushing a local directory to github: There are contents in the directory or its a empty directory
   1. ```git init``` to start tracking changes in the directory
   2. ```git add filename```(s) to start tracking changes in the file
   3. ```git commit -m "created file"```
   4. All changes are done now and you want to put the directory to remote i.e. github
   5. Create a repo on github. Do not initialize README.md file
   6. Push an existing repository from command line (skip first 4 steps) :
      ```echo "# notes4ref" >> README.md     
	  git init   
	  git add README.md
      git commit -m "first commit"
      git remote add origin link-to-your-repo.git
      git push -u origin master```

```git status``` will give you the current status of the changes in your directory. 
There are 3 states of a file:
* <font color= 'red'>red</font> (untracked files): a new file is added/ created or when the file has not been tracked for changes
* <font color= 'green'>green</font>: Staged and ready to be committed. 
* <font color= 'red'>red</font> (modified): some changes have been done to the file(s) and has not been commited yet


Other frequently used commands:
* ```git log```: tells us the history of commits for this file.
			most recent changes are shown on top. 
* ```git add filename```: adds changes to the file in the staging area
* ```git commit```: used for saving logical changes. 
			   git does not add changes to a commit automatically. 
			   You need to indicate which file and changes need to be saved before running the Git commit command. 
			   The commit command does not save changes in remote servers, only in the local repository of git
* ```git push remote-name branch-name ``` Syntax of git push. Push our changes to the remote server named origin from the master branch
* ```git pull``` get the remote changes to my local working directory

## How to:

* How to reset local changes you made to file to a previous commit? (before git add)
```git checkout HEAD filename```  
(If you specify "HEAD" as the revision, you will restore the last committed version of the file, effectively undoing any local changes that you current have in that file)

* How to make corrections to a file? (after git add i.e. file is in staging area)
```git reset filename```

* How to reset changes after commiting?
```git reset HEAD~1```

* How to go to a previous version of a file? (going back to a file as it was few commits ago)
```git checkout HEAD~3 filename```  here 3 is the commit number from head

* How to see difference between what is the staged area and our previous commit?
```git diff --staged```

* How to compare current file changes to a previous commit version?
```git diff 7_chars_previous_commit_id filenanme```

* How to see staged/comitted files:
```git status```

* How to rename a file once it is in the initialized git repo locally?
```mv oldname newname```

* How can I see what has changed in a file before committing to git?
```git diff filename```

* How to create a new branch?
```git branch branchname```

* How to list braches?
```git branch ```

* How to switch branch?
```git checkout branchname_to_switch_to```

* How to push my changes to remote repository?
```git push origin master```

* How to recover (the file(s) needs to be added first) a accidently deleted file from local directory:
```git checkout filename``` 

* How to discard my changes in the working directory (local) and pull in the latest changes from remote?
1. ```git stash```
2. ```git pull```
3. ```git stash pop```

* What does it mean?
  **(master)** in front of the directory --> name of the current branch that you are in
   nothing to commit, working on tree clean --> this means that the files has been commited.

* What are **HEAD** references?
    * HEAD means (the reference to the) current commit
    * HEAD~1 means (the reference to) 1 commit before
    * HEAD~ ALSO means (the reference to) 1 commit before
    * HEAD~87 means (the reference to) 87 commits before

    * ```git checkout HEAD~1``` will actually GO/checkout to 1 commit/reference before
    * ```git reset HEAD~3``` will uncommit your last 3 commits — without removing the changes,ie you can see all the changes made in the last 3 commits together, remove anything you don't like or add onto it and then commit them all again.
    * ```git diff HEAD~3``` for checking changes in the last 3 commits
   



## Best Practices:
* Make sure you are always using the latest code from remote origin. Before you do any changes:
   * ```git fetch```
   * ```git pull```
* Use command line to make any os level changes.
* Commit messages should be descriptive.
* Use reset if you want to undo staging of a modified file.
* Use `checkout` if you want to discard changes to unstaged file/s.
Option of reset:
     
   * ```--hard```: removes the changes that we have added to the file.
     
   * ```--soft```: removes the commit. doesnt change what happened in the staging area. doesnt change the file
     
   * ```--mixed```: removes the commit and also makes the changes unstaged. doesnt change the file
   

Learning Resourses:
* https://git-scm.com/book/en/v2
* https://www.git-tower.com/learn/git/videos
