## Restoring a Deleted File

### Introduction
In Git, you can restore a deleted file by retrieving it from a previous commit. This section outlines the steps to restore a deleted file in your Git repository.

### Deleting a File

#### 1. Remove the File
```bash
git rm toc.txt
```
- Deletes the specified file from the working directory and stages the deletion for the next commit.

#### 2. Commit Changes
```bash
git commit -m "Remove toc file"
```
- Commits the deletion of the file with an appropriate commit message.

### Restoring the Deleted File

#### 3. View Commit History
```bash
git log --oneline
```
- Displays the commit history to identify the previous state of the file.

#### 4. Locate Previous State
```bash
git checkout a642e12 toc.txt
```
- Checks out the specific commit (`a642e12`) where the file existed before deletion, restoring the file to its previous state.

### Finalizing Changes

#### 5. Review Changes
```bash
git status -s
```
- Verifies that the deleted file has been restored to the working directory.

#### 6. Commit Restoration
```bash
git commit -m "Restore toc file"
```
- Commits the restoration of the file with an appropriate commit message.

### Conclusion
By leveraging Git's version control capabilities, you can easily restore a deleted file by retrieving it from a previous commit. This process allows you to maintain the integrity of your project's history and recover lost files when needed.