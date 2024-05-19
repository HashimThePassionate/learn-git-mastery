# Undo a faulty merge

### Command 1: `git log --oneline --all --graph`
- This command is used to display the commit history in a concise format with commit IDs and commit messages.
- `--oneline`: Shows each commit as a single line.
- `--all`: Displays all branches.
- `--graph`: Draws ASCII graph lines representing the commit history branches and merges.

### Output 1:
```
*   ad4f937 (HEAD -> master) Merge branch 'bugfix'
|\
| * d0e95c0 (bugfix) Commit passwords
| * 49a023f Bugfix branch
* | 4404bdd audience
* | d7d7464 master
* | 84d855e master branch
|/
* a642e12 Add header to all pages.
* 50db987 Include the first section in TOC.
* 555b62e Include the note about committing after staging the changes.
* 91f7d40 Explain various ways to stage changes.
* edb3594 First draft of staging changes.
* 24e86ee Add command line and GUI tools to the objectives.
* 36cd6db Include the command prompt in code sample.
* 9b6ebfd Add a header to the page about initializing a repo.
* fa1b75e Include the warning about removing .git directory.
* dad47ed Write the first draft of initializing a repo.
* fb0d184 Define the audience.
* 1ebb7a7 Define the objectives.
* ca49180 Initial commit.
```

### Command 2: `git reset --hard HEAD~1`
- This command is used to reset the repository to a previous commit, discarding all changes after that commit.
- `--hard`: Resets both the working directory and the staging area to match the specified commit.

### Output 2:
```
HEAD is now at ad4f937 Merge branch 'bugfix'
```
```
* 4404bdd (HEAD -> master) audience
* d7d7464 master
* 84d855e master branch
| * d0e95c0 (bugfix) Commit passwords
| * 49a023f Bugfix branch
|/
* a642e12 Add header to all pages.
* 50db987 Include the first section in TOC.
* 555b62e Include the note about committing after staging the changes.
* 91f7d40 Explain various ways to stage changes.
* edb3594 First draft of staging changes.
* 24e86ee Add command line and GUI tools to the objectives.
* 36cd6db Include the command prompt in code sample.
* 9b6ebfd Add a header to the page about initializing a repo.
* fa1b75e Include the warning about removing .git directory.
* dad47ed Write the first draft of initializing a repo.
* fb0d184 Define the audience.
* 1ebb7a7 Define the objectives.
* ca49180 Initial commit.
```

### Command 3: `git reset --hard ad4f937`
- This command resets the repository to the state of the specified commit `ad4f937`, discarding all changes made after that commit.

### Output 3:
```
HEAD is now at ad4f937 Merge branch 'bugfix'
```
```
*   ad4f937 (HEAD -> master) Merge branch 'bugfix'
|\
| * d0e95c0 (bugfix) Commit passwords
| * 49a023f Bugfix branch
* | 4404bdd audience
* | d7d7464 master
* | 84d855e master branch
|/
* a642e12 Add header to all pages.
* 50db987 Include the first section in TOC.
* 555b62e Include the note about committing after staging the changes.
* 91f7d40 Explain various ways to stage changes.
* edb3594 First draft of staging changes.
* 24e86ee Add command line and GUI tools to the objectives.
* 36cd6db Include the command prompt in code sample.
* 9b6ebfd Add a header to the page about initializing a repo.
* fa1b75e Include the warning about removing .git directory.
* dad47ed Write the first draft of initializing a repo.
* fb0d184 Define the audience.
* 1ebb7a7 Define the objectives.
* ca49180 Initial commit.
```

### Command 4: `git revert HEAD`
- This command attempts to revert the changes introduced by the last commit (`HEAD`). However, since the last commit is a merge commit, Git requires the `-m` option to specify which parent's changes to revert.

### Output 4:
```
error: commit ad4f937b752ab7c24b241ccd6d7beafe5d065cd7 is a merge but no -m option was given.
fatal: revert failed
```

### Command 5: `git revert -m 1 HEAD`
- This command reverts the changes introduced by the last commit (`HEAD`) by creating a new commit that cancels out those changes. The `-m 1` option specifies to revert to the changes on the first parent branch.

### Output 5:
```
[master 56ea239] Revert "Merge branch 'bugfix'"
 2 files changed, 1 insertion(+), 3 deletions(-)
 delete mode 100644 password.txt
```
```
* 56ea239 (HEAD -> master) Revert "Merge branch 'bugfix'"
*   ad4f937 Merge branch 'bugfix'
|\
| * d0e95c0 (bugfix) Commit passwords
| * 49a023f Bugfix branch
* | 4404bdd audience
* | d7d7464 master
* | 84d855e master branch
|/
* a642e12 Add header to all pages.
* 50db987 Include the first section in TOC.
* 555b62e Include the note about committing after staging the changes.
* 91f7d40 Explain various ways to stage changes.
* edb3594 First draft of staging changes.
* 24e86ee Add command line and GUI tools to the objectives.
* 36cd6db Include the command prompt in code sample.
* 9b6ebfd Add a header to the page about initializing a repo.
* fa1b75e Include the warning about removing .git directory.
* dad47ed Write the first draft of initializing a repo.
* fb0d184 Define the audience.
* 1ebb7a7 Define the objectives.
* ca49180 Initial commit.
```

### Explanation:
- The first command `git log --oneline --all --graph` displays the commit history graphically.
- The second command `git reset --hard HEAD~1` resets the repository to the state before the last commit, effectively removing the faulty merge commit.
- The third command `git reset --hard ad4f937` resets the repository to the state of the specified commit, restoring the faulty merge commit.
- The fourth command `git revert HEAD` attempts to revert the changes