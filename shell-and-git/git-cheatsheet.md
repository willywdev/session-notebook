# Git Cheatsheet

## SETUP & INIT

| Git command     | Git task                                                     |
| --------------- | ------------------------------------------------------------ |
| git init        | initialize an existing directory as a Git repository         |
| git clone [URL] | retrieve an entire repository from a hosted location via URL |

## STAGE & SNAPSHOT

| Git command                      | Git task                                                              |
| -------------------------------- | --------------------------------------------------------------------- |
| git status                       | show modified files in working directory, staged for your next commit |
| git add [file]                   | add a file as it looks now to your next commit (stage)                |
| git commit -m "[commit message]" | commit your staged content as a new commit snapshot                   |
| git restore [file]               | Return to the last commited state of the file                         |

## INSPECT & COMPARE

| Git command | Git task                                                |
| ----------- | ------------------------------------------------------- |
| git log     | show the commit history for the currently active branch |

## SHARE & UPDATE

| Git command                   | Git task                                                                                |
| ----------------------------- | --------------------------------------------------------------------------------------- |
| git remote add [branch] [url] | Connect to an external repository (like Github for example). Default branch is `origin` |
| git push                      | Transmit local branch commits to the remote repository                                  |
| git pull                      | Transmit remote branch commits to local repository                                      |

## Branching

| Command                    | Description          |
| -------------------------- | -------------------- |
| git switch -c [branchname] | creates a new branch |
| git switch [branchname]    | switch branches      |
| git branch                 | show all branches    |
