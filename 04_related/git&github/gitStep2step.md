# Git step by step note

0. git configuration command
```
  git config --global user.name  'XXX'
  git config --global user.email 'abc@123.com'

```

1. local operation commands
```
  git init  // initial local repo

  git add <files> // add files to staging area

  git rm --cached <files> // remove files from the stating area

  git commit  -m ' ... '  // commit change in staging area

  git push // push to repo


```

2. status check commands

```
  git status // Check status of working tree

  git log  // Check activity log

```

3. Github part commands

```
  git remote add [name] [URL] [master]

  git push -u [name] [master]

  git pull // pull lastest from remote repo

  --------------------------------------------------
  git clone [URL]
```

4. Git branch commands

```
  git branch   // check how many and what branches we have
  git branch <branch-name>  // create a new branch with <branch-name>
  git checkout <branch-name> // switch to another git branch
  

  git checkout  <commit code> // go back to an historical commit.
  git checkout  -b <new-branch-name> // create a new branch and checkout to it


  git branch -d <name> //delete unnecessary branch
```

5. Merge command
```
  // first step, checkout to the branch which you want to include changes from other branches.
  // presume we are in the master branch and we want to merge codes from dev branch 


  git merge dev 
  //then we should push the changes to update the reop
  git push
```
 git relate files
.gitignore files 
log.txt