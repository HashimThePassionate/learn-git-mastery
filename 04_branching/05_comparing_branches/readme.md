# Comparing Branches

## Overview
This section covers how to compare branches and view the differences between them.

## Step 1: Switch to the main branch
Ensure you're on the main branch (e.g., master) before comparing with another branch:
```bash
git switch master
```

## Step 2: View commits not in the main branch
To see the commits that exist in another branch but not in the main branch, use:
```bash
git log --oneline master..bugfix
```
This command displays the commits exclusive to the "bugfix" branch.

## Step 3: View the actual changes between branches
To see the actual changes between branches, you can use:
```bash
git diff master..bugfix
```
This command shows the differences in content between the main branch and the "bugfix" branch.

## Step 4: Shortcut for comparing branches
If you're already on the main branch, you can use a shorthand to compare directly with another branch:
```bash
git diff bugfix
```

## Step 5: View only the names of changed files
To see only the names of files that are different between branches, use:
```bash
git diff --name-only bugfix
```

## Step 6: View status of changed files
To see the status (modified, added, deleted) of files that are different between branches, use:
```bash
git diff --name-status bugfix
```

## Conclusion
Comparing branches allows you to understand the differences in code between different development branches, aiding in code review and merging decisions.
```