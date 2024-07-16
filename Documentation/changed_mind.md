
## Changed your mind?
### Reverting changes
#### Modify the lastest version of with unwanted comments,then revert it back to its original state before staging using Git command
* check current content of hello.sh file
```
cat hello.sh
```
* modify hello.sh with unwanted comments
* Revert changes before staging
```
git checkout -- hello.sh
```
* check content of hello.sh after reverting
```
cat hello.sh
```
### Staging and Cleaning
* Introduce unwanted changes to hello.sh
* Staging the changes
```
git add hello.sh
```
```
git status
```
* Clean the staging area to discard changes
```
git reset HEAD hello.sh
```
* Status after cleaning the staging area
```
git status
```
* Discard changes in working directory
```
git checkout -- hello.sh
```
* Final content of hello.sh
```
cat hello.sh
```
### Committing and Reverting
* Introduce unwanted changes to hello.sh
* show updated content of hello.sh
```
cat hello.sh
```
* Staging and committing the changes
```
git add hello.sh
```
```
git commit -m "feat: introduce unwanted changes(to be reverted)"
```
```
git status
```
* Show the last commit
```
git log -n 1
```
* Revert the last commit
```
git revert HEAD --no-edit
```
```
git status
```
```
cat hello.sh
```
### Tagging and Removing Commits
* show current state of the repository
```
git log --oneline -n 5
```
* Tag the lastest commit with 'oops'
```
git tag oops
```
* Verify the 'oops' tag
```
git show oops --oneline
```
* Locate the v1 tag
```
git show v1 --oneline
```
* Remove commits made after v1 and point HEAD to v1
```
git reset --hard v1
```
* Verify that HEAD now points to v1
```
git log --oneline -n 1
```
* Show all tags
```
git tag -l
```
* Show the state of the repository
```
git log --oneline --decorate -n 5
```
### Displaying logs with Deleted Commits
* Display full reflog
```
git reflog
```
* Display reflog entries with 'oops' tag
```
git reflog show oops
```
* Show details of 'oops' commit
```
git show oops
```
### Cleaning Unreferenced commits
* Current reflog before cleaning 
```
git reflog
```
* Clean unreferenced objects
```
git reflog expire --expire=now --all
```
* Run garbage collection
```
git gc --prune=now
```
* Reflog after cleaning
```
git reflog
```
* Verify unreachable objects
```
git fsck
```
### Author Information
* Add author information to hello.sh
* commit changes
```
git add hello.sh
```
```
git commit -m "feat: add author info"
```
* Show commit log
```
git log -n 1 --pretty=format:"%h - %an, %ar : %s"
```
* Update file with author email
* Amend the previous commit with the updated file
```
git add hello.sh
```
```
git commit --amend --no edit
```
* show updated commit log
```
git log -n 1 --pretty=format: "%h - %an, %ar : %s"
```