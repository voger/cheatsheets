My own git cheatsheet and some guides.

1. Never write in master. Always use branches
2. Master is only for good production ready code.


## Branches

Command                                 | Description
----------------------------------------|------------------------------------
 **git branch <new_feature>**          |**Create** new branch
 **git branch <fixing_readme> cef45ff** |Create new branch from an arbitrary commit
 **git checkout <new_feature>**        |**Checkout** new branch
 **git checkout -b <new_feature>**     |**Create** and **checkout** new branch
 **git branch -d <new_feature>**       |**Delete** branch new_feature
 **git branch -D <new_feature>**       |**Delete** branch new_feature even if it is not merged (**--force**)
**git log --graph --decorate --pretty=oneline --all --abbrev-commit**|**Pretty print** the development tree
**git stash**                           |**Stash** the work in progress in current branch
**git stash list**                      |See a list of stashed WIP's
**git stash pop**                       |**Pop** stashed WIP

## Commit

Command  | Description
-------------------------------|----------------
**git add .**                  | **Add** everything to the stagging area
**git commit -m "New message"**| **Commit** stagging area
**git -am "New message"**      | **Add** and **commit**. *Shortcut*
