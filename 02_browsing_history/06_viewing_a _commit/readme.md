## Viewing a Commit

### Introduction
Git provides the `git show` command to display detailed information about a specific commit. This section demonstrates how to view a commit and its changes using different options.

### Viewing Commit Details

#### 1. `git show HEAD~2`
- Displays detailed information about the commit located two steps before the current HEAD (HEAD~2).
- This includes the commit message, author, date, and the changes introduced in the commit.
  
#### 2. `git show HEAD~2 --name-only`
- Shows only the names of the files that were modified, added, or deleted in the specified commit.
- Useful for quickly identifying the files affected by the commit without displaying the actual changes.

#### 3. `git show HEAD~2 --name-status`
- Displays the names of the files modified, added, or deleted in the commit along with the status of each change (modified, added, deleted).
- Provides a concise summary of the changes made in the commit.

### Conclusion
Using the `git show` command, you can inspect the details of a specific commit, including its changes and the files affected. By specifying different options such as `--name-only` or `--name-status`, you can tailor the output to suit your requirements, whether you need a detailed view of the changes or just a summary of the affected files.