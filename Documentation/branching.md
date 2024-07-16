
## Branching
* Create and switch to the new branch
```
git checkout -b greet
```
```
cd lib/
```
* Create the greeter.sh file and update content
```
touch greeter.sh
```
* Add and commit the new file
```
git add greeter.sh

git commit -m "feat: add greeter.sh file with Greeter function"
```
* Update the lib/hello.sh file
* Stage and commit the changes
```
git add lib/hello.sh
git commit -m "feat: update hello.sh file to use Greeter function"
```
* Update the Makefile
* Stage the Makefile
```
git add Makefile
```
* Commit the changes
```
git commit -m "feat: update Makefile to run updated lib/hello.sh"
```
* Switch back to master branch
```
git checkout master
```
* Compare Makefile between master and greeter branch
```
git diff master..greet -- Makefile
```
* compare hello.sh between master and greeter branch
```
git diff master..greet -- lib/hello.sh
```
* Compare greeter.sh between master and greeter branch
```
git diff master..greet -- lib/greeter.sh
```
* Create README.md
* Stage and commit the new file
```
git add README.md

git commit -m "feat: add the initial README.md"
```
* Draw a commit tree diagram to show the diverging changes between all branches to demonstrate the branch history
```
git log --graph
```