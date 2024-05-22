# Squash merge

### Command 1: `git switch -C bugfix/photo-upload`
- This command creates a new branch named `bugfix/photo-upload` and switches to it.

### Output 1:
```
Switched to a new branch 'bugfix/photo-upload'
```

### Command 2: `echo bugfix >> audience.txt` and `git commit -am "update audience.txt"`
- These commands add the text "bugfix" to the `audience.txt` file and commit the changes.

### Output 2:
```
1 file changed, 1 insertion(+), 1 deletion(-)
```

### Command 3: `echo bugfix >> toc.txt` and `git commit -am "update toc.txt"`
- These commands add the text "bugfix" to the `toc.txt` file and commit the changes.

### Output 3:
```
1 file changed, 1 insertion(+), 1 deletion(-)
```

### Command 4: `git log --oneline --all --graph`
- This command displays the commit history graphically.

### Output 4:
```
* b9d8cbd (HEAD -> bugfix/photo-upload) update toc.txt
* 1770ea9 update audience.txt
* 56ea239 (master) Revert "Merge branch 'bugfix'"     
*   ad4f937 Merge branch 'bugfix'
|\
| * d0e95c0 Commit passwords
| * 49a023f Bugfix branch
* | 4404bdd audience
* | d7d7464 master
* | 84d855e master branch
|/
* a642e12 Add header to all pages.
* 50db987 Include the first section in TOC.
* 555b62e Include the note about committing after staging the changes.
...
```

### Command 5: `git switch master` and `git merge --squash bugfix/photo-upload`
- These commands switch back to the `master` branch and perform a squash merge of the changes from the `bugfix/photo-upload` branch into the `master` branch.

### Output 5:
```
Updating 56ea239..b9d8cbd
Fast-forward
Squash commit -- not updating HEAD
 audience.txt | 2 +-
 toc.txt      | 2 +-
 2 files changed, 2 insertions(+), 2 deletions(-)
```

### Command 6: `git status -s`
- This command shows the status of the working directory in a short format.

### Output 6:
```
M  audience.txt
M  toc.txt     
```

### Command 7: `git commit -am "Squash Merge"`
- This command commits the changes resulting from the squash merge with a message "Squash Merge".

### Output 7:
```
[master 2ced86d] Squash Merge
 2 files changed, 2 insertions(+), 2 deletions(-)
```

### Command 8: `git log --oneline --all --graph`
- This command displays the updated commit history after the squash merge.

### Output 8:
```
* 2ced86d (HEAD -> master) Squash Merge
| * b9d8cbd (bugfix/photo-upload) update toc.txt
| * 1770ea9 update audience.txt
|/
* 56ea239 Revert "Merge branch 'bugfix'"
*   ad4f937 Merge branch 'bugfix'
|\  
| * d0e95c0 Commit passwords
| * 49a023f Bugfix branch
* | 4404bdd audience
...
```

### Command 9: `git branch -D bugfix/photo-upload`
- This command deletes the `bugfix/photo-upload` branch.

### Command 10: `git log --oneline --all --graph`
- This command displays the final commit history after deleting the `bugfix/photo-upload` branch.

### Output 10:
```
* 2ced86d (HEAD -> master) Squash Merge
* 56ea239 Revert "Merge branch 'bugfix'"
*   ad4f937 Merge branch 'bugfix'
|\  
| * d0e95c0 Commit passwords
| * 49a023f Bugfix branch
* | 4404bdd audience
...
```

### Explanation:
- The first few commands create a new branch `bugfix/photo-upload`, make some changes, and commit them.
- Then, a squash merge is performed to merge the changes from the `bugfix/photo-upload` branch into `master`.
- After committing the squash merge, the `bugfix/photo-upload` branch is deleted, leaving a clean commit history on the `master` branch.