
## Conflicts,merging and rebasing
### Merge Master into Greet Branch
* Switch to the greet branch
```
git checkout greet
```
* Merge master into greet branch
```
git merge master
```
* Switch to the master branch
```
git checkout master
```
* Update the content of hello.sh
* Commit the changes
```
git add lib/hello.sh

git commit -m "feat: update hello.sh to prompt for user's name"
```

### Merging master into Greet branch(Conflict)
* Attempted to merge master into greet
```bash
git checkout greet
git merge master
```
### Rebasing Greet Branch 
* Reset the greet branch to the point before the initial merge
```
git checkout greet 
git reset --hard HEAD~1
git rebase master
```
### Merging Greet into Master
* Merge the changes from the greet branch into the master branch
```
git checkout main
git merge greet
```

## Understanding Fast-Forwarding, Merging, and Rebasing

### Fast-Forwarding

Fast-forwarding in Git occurs when the branch you're merging into hasn't diverged from the branch you're merging. In other words, all the commits in the branch being merged are directly ahead of the target branch.

- **Example**: If `master` hasn't changed since we created `greet`, merging `greet` into `master` would be a fast-forward.
- **Result**: The branch pointer simply moves forward to the latest commit. No new commit is created.
- **Advantage**: Maintains a linear history.

### Merging vs. Rebasing

Both merging and rebasing are ways to integrate changes from one branch into another, but they do so in different ways.

#### Merging

- **Process**: Creates a new "merge commit" that ties together the histories of both branches.
- **History**: Preserves the branch structure and shows when a merge occurred.
- **Use Case**: Good for preserving the context of a branch and when you want to maintain the exact history of your project.

#### Rebasing

- **Process**: Moves the entire feature branch to begin on the tip of the main branch, effectively incorporating all new commits in main.
- **History**: Results in a linear project history.
- **Use Case**: Useful for keeping a cleaner, more linear history, especially before merging a feature branch into main.

### Key Differences

1. **History Preservation**:
   - Merging preserves the entire history and branch structure.
   - Rebasing rewrites the project history by creating new commits for each commit in the original branch.

2. **Conflict Resolution**:
   - In a merge, you resolve conflicts only once, in the merge commit.
   - In a rebase, you may need to resolve conflicts for each commit being rebased.

3. **When to Use**:
   - Merge when you want to preserve the context of a feature branch.
   - Rebase when you want to maintain a linear history and are working on a branch that hasn't been shared with others.

4. **Collaboration Impact**:
   - Merging is generally safer for branches that are shared with other developers.
   - Rebasing shared branches can cause issues for collaborators, as it rewrites history.

In our exercise:
1. We first rebased `greet` onto `master`, which moved our `greet` commits to start from the tip of `master`.
2. This allowed for a fast-forward merge when we later merged `greet` into `master`.
3. The result is a linear history that incorporates all changes as if they were developed sequentially, even though they were developed in parallel.