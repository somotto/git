

## Bare repositories

### What is a bare repository and why is it needed?
    A bare repository is a special type of Git repository that:

     1. Does not contain a working directory.
     2. Only contains the contents of what you'd normally find in the `.git` directory of a regular repository.
     3. Is typically used as a central repository that other repositories can clone from or push to.
  
   * Why are Bare Repositories Needed?

     1. **Central Repository**: They serve as a centralized point for collaboration, where multiple developers can push to and pull from.

     2. **Avoiding Conflicts**: Since there's no working directory, there's no risk of conflicts between the repository's state and a working copy.

     3. **Server-Side Efficiency**: They're more efficient for server-side repositories as they don't need to maintain a working copy of all files.

     4. **Hooks and Automation**: Bare repositories are ideal for implementing server-side hooks and automation scripts.

     5. **Storage Optimization**: They only store the Git database, saving space compared to non-bare repositories.
 
### Create a bare repository named hello.git from the existing hello repository.
 ```
 git clone --bare hello hello.git
 ```

  * Verifying the bare repo when in the hello.git
  ```
  git config --get core.bare
  ```
### Add the bare hello.git repository as a remote to the original repository hello.
  * Go to the original hello repository
    ```
    cd ../hello
    ```

  * Add the bare repository as a remote
   ```
   git remote add bare ../hello.git
   ```

### Change the README.md file in the original repository 
   * Update its content
   * Add the updated README.md 
    ```
    git add README.md
    ```
  * Commit and push
  ```
  git commit -m "feat: update README.md in original repo"
  git push origin master
  ```
### Switch to the cloned repository cloned_hello and pull down the changes just pushed to the shared repository
   * Change to the cloned repo
    ```
    cd cloned_hello
    ```

  * Fetch the lastest changes from the remote repository
   ```
   git fetch upstream

   git pull upstream master
   ```

  * Verify the changes
   ```
   git log --oneline -n 5
   ```






