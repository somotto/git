
## Move it
* Check current directory structure
```
ls -R
```
* Create lib/ directory
```
mkdir -p lib
```
* Move hello.sh to lib/ using git
```
git mv hello.sh lib/
```
* Check the new directory structure
* Check git status
* Commit the move
```
git commit -m "feat: move hello.sh to lib/ directory"
```
* Show commit log
```
git log -n 1 --pretty=format:"%h - %an, %ar : %s"
```

* Create Makefile in the root directory
```
touch Makefile
```
* update the provided content
* commit the file to the repo
```
git add Makefile
```
```
git commit -m "feat: add Makefile with run target for hello.sh"
```