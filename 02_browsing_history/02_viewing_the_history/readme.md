## Viewing the History

### Introduction
The `git log` command in Git allows you to view the commit history of a repository. It provides detailed information about each commit such as the unique identifier, author details, date, commit message, and more.

### Basic Usage

#### 1. `git log`
- Displays the commit history with detailed information including:
  - Unique identifier (SHA)
  - Author Name
  - Author Email
  - Date
  - Commit Message
- **Example Output:**
```
commit 07a10f93b3f6cde44fc72f0ad8f7cd7719caa9cb
Author: Muhammad Hashim <*****@gmail.com>
Date:   Mon May 6 00:43:15 2024 +0500

    Creating Snapshots with vs code
```

#### 2. `git log --oneline`
- Displays a concise summary of each commit in a single line.
- **Example Output:**
```
07a10f9 (Muhammad Hashim 2024-05-06) Creating Snapshots with vs code
```

### Additional Options

#### 3. `git log --oneline --stat`
- Shows summary and statistics for each commit, including the files that have been changed.
- **Example Output:**
```
07a10f9 (Muhammad Hashim 2024-05-06) Creating Snapshots with vs code
 README.md | 6 ++++--
 1 file changed, 4 insertions(+), 2 deletions(-)
```

#### 4. `git log --stat`
- Provides detailed statistics about each commit, including the number of insertions and deletions per file.
- **Example Output:**
```
commit 07a10f93b3f6cde44fc72f0ad8f7cd7719caa9cb
Author: Muhammad Hashim <*****@gmail.com>
Date:   Mon May 6 00:43:15 2024 +0500

    Creating Snapshots with vs code

 README.md | 6 ++++--
 1 file changed, 4 insertions(+), 2 deletions(-)
```

#### 5. `git log --oneline --patch`
- Shows the actual changes made in each commit.
- **Example Output:**
```
07a10f9 (Muhammad Hashim 2024-05-06) Creating Snapshots with vs code
diff --git a/README.md b/README.md
index 1234567..8901234 100644
--- a/README.md
+++ b/README.md
@@ -1,4 +1,6 @@
 # Viewing the history
 // Lets learn bit more about "log" command
+
+## Some new changes
```

#### 6. `git log <commit-SHA> --oneline --patch`
- Shows the actual changes made in a specific commit identified by its SHA.
- **Example Output:**
```
07a10f9 (Muhammad Hashim 2024-05-06) Creating Snapshots with vs code
diff --git a/README.md b/README.md
index 1234567..8901234 100644
--- a/README.md
+++ b/README.md
@@ -1,4 +1,6 @@
 # Viewing the history
 // Lets learn bit more about "log" command
+
+## Some new changes
```

### Conclusion
Understanding how to use `git log` and its various options can provide valuable insights into the commit history of a Git repository, aiding in project management and collaboration.