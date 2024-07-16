## Local and remote repositories
### In the work/ directory, make a clone of the repository hello
```
git clone hello cloned_hello
```
### Show the logs for the cloned repository
```
cd cloned_hello
git log --oneline --graph --all
```
### Display the name of the remote repository and provide more information about it
  * Display the name of the remote repository
  ```
  git remote
  ```
  * Get more detailed information about the remote
  ```
  git remote -v
  ```
  * More information 
  ```
  git remote show origin
  ```

### List all remote and local branches in the cloned_hello repository.  
```
git branch -a
```

### Updating the Original Repository
  * Navigate to the original repository
  ```
  cd ../hello
  ```
  * Update the README.md
  * Stage the changes
  ```
  git add README.md
  ```
  * Commit the changes
  ```
  git commit -m "feat: update README.md in the original repository"
  ```

### Inside the cloned repository (cloned_hello), fetch the      changes from the remote repository and display the logs. Ensure that commits from the hello repository are included in the logs.
  * Navigate to the cloned_hello
  ```
  cd ../cloned_hello
  ```
  * Fetch changes from the remote repository
  ```
  git fetch origin
  ```
  * Display the logs, including all branches
  ```
  git log --all --oneline --graph
  ```

### Merge the changes from the remote master branch into the local master branch
```
git merge origin/master
```

### Add a local branch named greet tracking the remote origin/greet branch
   * Create a new local branch greet that tracks the remote origin/greet branch
   ```
   git checkout -b greet origin/greet
   ```
   * Verifying the new branch
   ```
   git branch -vv
   ```
### Add a remote to your Git repository and push the main and greet branches to the remote.
  * Add a new remote 
  ```
  git remote add upstream https://learn.zone01kisumu.ke/git/somotto/git.git
  ```

  * Push the master branch
  ```
  git push upstream master
  ```
  * Push the greet branch
   ```
   git push upstream greet
   ``` 
### What is the single git command equivalent to what you did before to bring changes from remote to local main branch?"
  ```
  git pull origin master
  ```