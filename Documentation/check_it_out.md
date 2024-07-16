
## Check it out
### Restore First Snapshot
* Capture the first snapshot of the working tree
```
git log --reverse --oneline | head -1
```
* Checkout this commit(make it the head)
```
git checkout d28f693
```
* Print the content of the hello.sh file
```
cat hello.sh
```
### Restore Second Recent Snapshot
* Capture the second snapshot of the working tree
```
git log --oneline -n 2 | tail -n 1
```
* Checkout this commit(make it the head)
```
git checkout HEAD~1
```
* Print the content of the hello.sh
```
cat hello.sh
```
### Return to Lastest Version
```
git checkout master
```
```
cat hello.sh
```