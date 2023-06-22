# Git Cheatsheet

---

## Creating local repo

`cd path/to/my/folder`
`git init`

❗️ Don't init a repo inside a repo
To check:
`git status`

## Different Stages of Files

**Untracked** or **Tracked**
Untracked files have not been added to git.

### Tracked Files

| state     | description                        |
| --------- | ---------------------------------- |
| modified  | has changes since the last commit  |
| staged    | is included in next commit         |
| committed | all changes have been saved in git |
