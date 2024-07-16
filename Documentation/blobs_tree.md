
## blobs,trees abd commits
### Exploring .git/ Directory
* Contents of .git/:
```
ls -la .git/
```
* Contents of .git/objects/:
```
ls -la .git/objects/
```
* Contents of .git/refs/:
```
ls -la .git/refs/
```
* Contents of .git/config:
```
cat .git/config
```
* Contents of .git/HEAD:
```
cat .git/HEAD
```
### Latest Object Hash
* Find the lastest object file
```
find .git/objects -type f ! -path ".git/objects/pack/*" -printf '%T@ %p\n' | sort -n | tail -1 | cut -f2- -d" "
```
* Extract the hash from the path
```
echo $latest_object | sed 's/.*objects\/\(..\)\/\(.*\)/\1\2/'
```
* Get object type
```
git cat-file -t <hash>
```
* Get object content
```
git cat-file -p <hash>
```
### Dumping the Directory Tree
* Get lastest commit hash
```
git rev-parse HEAD
```
* Dump directory tree
```
git ls-tree -r <commit_hash>
```
* Dump contents of lib/directory
```
git ls-tree <commit_hash>:lib
```
* Dump contents of hello.sh file
```
git show <commit_hash>:lib/hello.sh
```