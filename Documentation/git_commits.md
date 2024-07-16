## Git commits to commit
### Make work directory
```
mkdir work
```
```
cd work
```
### Creating hello subdirectory and hello.sh file
```
mkdir hello
```
```
cd hello
```
```
echo 'echo "Hello, World"' > hello.sh
```
### initialize the git repository
```
git init
```
```
git status
```
```
git add hello.sh
```
### Changing hello.sh content, staging, and committing
* Change hello.sh content

* Stage the changed file
```
git add hello.sh
```

* Commit the changes
```
git commit -m "Update hello.sh to accept a command-line argument"
```

* Verify that the working tree is clean
```
git status
```
## Modifying hello.sh and making two separate commits

* Modify hello.sh content

* Stage and commit the comment (line 3) separately
```
git add -p hello.sh
```
(Manually select only the hunk with the comment)
```
git commit -m "feat: add comment explaining default value"
```

* Stage and commit the changes to lines 4 and 5
```
git add hello.sh
```
```
git commit -m "feat: implement default value and use variable in echo statement"
```
* Verify that all changes are committed
```
git status
```