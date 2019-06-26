My own git cheatsheet and some guides.

1. Never write in master. Always use branches
2. Master is only for good production ready code.


1. [Branches](#branches)
2. [Log](#log)
3. [Commit](#commit)
4. [Clone](#clone)
5. [Rebase](#rebase)
6. [Remotes](#remotes)
7. [Reset](#reset)

## Branches

| Command                                       | Description                                                          |
|-----------------------------------------------|----------------------------------------------------------------------|
| **git branch <new_feature>**                  | **Create** new branch from current branch                            |
| **git branch <fixing_readme> cef45ff**        | Create new branch from an **arbitrary commit**                       |
| **git branch <fixing_readme> <other_branch>** | Create new branch from **another branch**                            |
| **git branch -m <new_name>**                  | Rename current branch                                                |
| **git branch -m <old_name> <new_name>**       | Rename a branch                                                      |
| **git checkout <new_feature>**                | **Checkout** new branch                                              |
| **git checkout -b <new_feature>**             | **Create** and **checkout** new branch                               |
| **git branch -d <new_feature>**               | **Delete** branch new_feature                                        |
| **git branch -D <new_feature>**               | **Delete** branch new_feature even if it is not merged (**--force**) |
| **git stash**                                 | **Stash** the work in progress in current branch                     |
| **git stash list**                            | See a list of stashed WIP's                                          |
| **git stash pop**                             | **Pop** stashed WIP                                                  |



## Log

| Command                                                               | Description                           |
|-----------------------------------------------------------------------|---------------------------------------|
| **git log --oneline**                                                 | Condensed view of log                 |
| **git log --graph --decorate --pretty=oneline --all --abbrev-commit** | **Pretty print** the development tree |



## Commit

| Command                          | Description                             |
|----------------------------------|-----------------------------------------|
| **git add .**                    | **Add** everything to the stagging area |
| **git commit -m "New message"**  | **Commit** stagging area                |
| **git commit -am "New message"** | **Add** and **commit**. *Shortcut*      |


## Clone

1. When cloning a repo only the active branch is cloned. The other branches can be seen by using `git branch --all` in the clone. They appear with the prefix `remotes/origin/<branch_name>`

| Command                           | Description                                                                            |
|-----------------------------------|----------------------------------------------------------------------------------------|
| **git clone <source\> <target\>** | **Clone** source by creating target. Source can be a local repo folder or remote repo. |

## Rebase

| Command                             | Description                                        |
|-------------------------------------|----------------------------------------------------|
| **git rebase master**               | **Rebase** current branch to the top of the master |
| **git rebase --interactive master** | **Squash** commits interactively.                  |

## Remotes

| Command                                                                   | Description                                            |
|---------------------------------------------------------------------------|--------------------------------------------------------|
| **git remote -v show**                                                    | Shows the **remote address** (folder, url or whatever) |
| **git ls-remote <remote\>**                                               | **List** remote branches                               |
| **git remote rename <old_name> <new_name\>**                              | **Rename** remote. E.g. origin to upstream             |
| **git remote add <name\> <remote address\>**                              | **Add** extra remote                                   |
| **git remote set-url origin git@github.com:username/your-repository.git** | **Change** remote address                              |
| **git push [<remote\> <branch\>]**                                        | **Push** branch to remote. If branch exists to remote  |
| **git push --set-upstream <remote\> new_branch**                          | **Create, Push and Track** new branch to remote        |
| **git push <remote\> :<branch\>**                                         | **Delete** branch from remote                          |
| **git pull**                                                              | **Pull** changes from remote                           |
| **git fetch**                                                             | **Fetch** change from remote but don't merge           |
| **git diff HEAD FETCH_HEAD**                                              | **see the diff** between HEAD and ***remote* HEAD      |
| **git merge HEAD FETCH_HEAD**                                             | **Merge** HEAD with FETCH_HEAD                         |


## Reset

| Command                                            | Description                                                        |
|----------------------------------------------------|--------------------------------------------------------------------|
| **git reset HEAD --hard**                          | Reset everything to the HEAD                                       |
| **git clean -f**                                   | Remove untracked **files**                                         |
| **git clean -fd**                                  | Remove untracked **files** and **directories**                     |
| **git clean -fdx**                                 | Remove **ignored** and **untracked** **files** and **directories** |
| **git reset -- <file>** && **git checkout <file>** | Restore deleted file                                               |
| **git reset -- filename**                          | Resvert a file back from HEAD                                      |
