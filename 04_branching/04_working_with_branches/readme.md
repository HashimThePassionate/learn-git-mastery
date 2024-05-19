# Working with Branches

## Overview
This guide demonstrates how to work with branches in a Git repository.

## Step 1: View all branches
To view all branches in the repository, use the command:
```bash
git branch
```

## Step 2: Create a new branch
Assuming we want to fix a bug, let's create a new branch named "BugFix":
```bash
git branch BugFix
```

## Step 3: Switch to the new branch
Switch to the newly created branch using:
```bash
git switch BugFix
```

## Step 4: Rename the branch (optional)
If desired, you can rename the branch for clarity. For example:
```bash
git branch -m BugFix bugfix-logout-form
```

## Step 5: Make changes in the branch
Make changes to files in the branch. For example, open a file and add/edit content:
```bash
code audience.txt
```

## Step 6: Add and commit changes
Add the changes to the staging area and commit them:
```bash
git add audience.txt
git commit -m "Fix the bug that prevented the users from logout"
```

## Step 7: View branch-specific commits
To view only the commits in the current branch, use:
```bash
git log --oneline
```

## Step 8: Switch back to the main branch
Switch back to the main branch (e.g., master):
```bash
git switch master
```

## Step 9: Delete the branch
If the branch is no longer needed, you can delete it. First, ensure it's fully merged, or force delete if not:
```bash
git branch -d bugfix-logout-form  # Delete if fully merged
git branch -D bugfix-logout-form  # Force delete
```

## Conclusion
Working with branches allows for isolating changes and managing development tasks efficiently in Git.
```