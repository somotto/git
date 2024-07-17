
## History
* Show the history of the working directory
```
git log
```
* Show One-line history of a condensed view showing only commit hashes and messages
```
git log --oneline
```
### Controlled Entries:
* Showing the last 2 entries in the log
```
git log -n 2
```
* Showing commits made within the last 5 minutes
```
git log --since="5 minutes ago"
```
### Personalized Format
```
git log --pretty=format:"*%h %ad | %s%d [%an]" --date=short
```