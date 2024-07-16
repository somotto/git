

## TAG me
### Referencing Current Version:
```
git tag v1
```
* Verifying the tag was created
```
git tag -l
```
* Tagging Previous Version
```
git tag v1-beta HEAD~1
```
### Navigating Tagged Versions:
* Checking out v1
```
git checkout v1
```
* Content of hello.sh in v1
```
cat hello.sh
```
* Checking out v1-beta
```
git checkout v1-beta
```
* Content of hello.sh in v1-beta
```
cat hello.sh
```
* Return to the master branch
```
git checkout master
```
### List all tags in the repository
```
git tag -l
```