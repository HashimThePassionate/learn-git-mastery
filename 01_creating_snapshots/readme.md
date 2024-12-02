# 📚 Git Fundamentals
 
## 📸 Creating Snapshots

Git is a powerful version control system that allows you to create snapshots of your project at different points in time. 📅 Below are some fundamental concepts you'll learn about creating snapshots in Git:

## 📑 Table of Contents

1. [**1. Initializing**](#1-initializing) 🔧
2. [**2. Staging Files**](#2-staging-files) 📂
3. [**3. Committing Changes**](#3-committing-changes) ✍️
4. [**4. Skipping Staging Area**](#4-skipping-staging-area) 🚀
5. [**5. Removing Files**](#5-removing-files) 🗑️
6. [**6. Renaming or Removing Files**](#6-renaming-or-removing-files) 🔄
7. [**7. Ignoring Files**](#7-ignoring-files) 🚫
8. [**8. Short Status**](#8-short-status) 📋
9. [**9. Viewing Staged and Unstaged Changes**](#9-viewing-staged-and-unstaged-changes) 🔍
10. [**10. Visual Diff Tools**](#10-visual-diff-tools) 🖥️
11. [**11. Viewing Commit History**](#11-viewing-commit-history) 📜
12. [**12. Viewing a Commit Exactly**](#12-viewing-a-commit-exactly) 🕵️
13. [**13. Unstaging Files**](#13-unstaging-files) 🔄
14. [**14. Discard Local Changes**](#14-discard-local-changes) ❌
15. [**15. Restoring a File to an Earlier Version**](#15-restoring-a-file-to-an-earlier-version) ⏪

By mastering these concepts, you'll have a solid understanding of how to manage snapshots and track changes effectively in Git. 🚀


## 🔧 1. Initializing

Initialize a new Git repository in your project directory to start tracking changes. This creates a hidden `.git` folder where Git stores all version history and configuration.

```sh
git init
```

*Example:*

```sh
cd your-project-directory
git init
```


## 📂 2. Staging Files

Use the staging area to prepare files for the next commit. Staging allows you to select which changes to include in a commit.

```sh
git add <file-name>
```

*Example:*

```sh
git add README.md
```

To stage all changes:

```sh
git add .
```


## ✍️ 3. Committing Changes

Commit your staged changes to the repository, creating a snapshot of your project at that moment. Each commit records the current state of the project along with a descriptive message.

```sh
git commit -m "Your commit message"
```

*Example:*

```sh
git commit -m "Add initial project structure"
```


## 🚀 4. Skipping Staging Area

Directly commit changes without staging them first using the `-a` flag. This is useful for quickly committing modified and deleted files.

```sh
git commit -a -m "Your commit message"
```

*Example:*

```sh
git commit -a -m "Fix bug in authentication module"
```

*Note:* This does not include new untracked files. Use `git add` to track new files before committing.


## 🗑️ 5. Removing Files

Remove files from both your working directory and the Git repository.

```sh
git rm <file-name>
```

*Example:*

```sh
git rm old-config.yml
```

To remove a file from the repository but keep it locally:

```sh
git rm --cached <file-name>
```

*Example:*

```sh
git rm --cached secrets.txt
```


## 🔄 6. Renaming or Removing Files

Rename or remove files while maintaining their history in Git. Renaming helps keep track of file movements.

```sh
git mv <old-file-name> <new-file-name>
```

*Example:*

```sh
git mv README.txt README.md
```

*Note:* After renaming, commit the changes to record the update.


## 🚫 7. Ignoring Files

Configure Git to ignore certain files or directories, such as temporary files or build artifacts, by using a `.gitignore` file.

1. **Create a `.gitignore` file** in your repository's root directory.

2. **Add patterns** to specify files or directories to ignore.

   *Example `.gitignore`:*

   ```
   # Ignore node_modules
   node_modules/

   # Ignore log files
   *.log

   # Ignore environment variables
   .env
   ```

*Tip:* Use `git rm --cached <file>` to stop tracking a file that's already been committed.


## 📋 8. Short Status

Check the current status of your repository in a concise format. This helps you quickly see which files are staged, unstaged, or untracked.

```sh
git status -s
```

*Example Output:*

```
 M README.md
?? new-file.js
```

*Legend:*
- `M`: Modified
- `??`: Untracked


## 🔍 9. Viewing Staged and Unstaged Changes

View the differences between the files in your working directory, the staging area, and the last commit to understand what has changed.

- **Staged Changes:**

  ```sh
  git diff --staged
  ```

- **Unstaged Changes:**

  ```sh
  git diff
  ```

*Example:*

```sh
git diff --staged
git diff
```


## 🖥️ 10. Visual Diff Tools

Utilize visual diff tools to compare changes between different versions of files. This provides a graphical interface for reviewing changes.

- **Using Git's Built-in Diff Tool:**

  ```sh
  git difftool
  ```

- **Configuring an External Diff Tool (e.g., Meld):**

  ```sh
  git config --global diff.tool meld
  ```

  Then use:

  ```sh
  git difftool
  ```

*Example:*

```sh
git difftool HEAD~1 HEAD
```


## 📜 11. Viewing Commit History

Explore the history of commits in your repository to understand how your project has evolved over time.

```sh
git log
```

*Enhanced Log View:*

```sh
git log --oneline --graph --decorate --all
```

*Example Output:*

```
* f3d2e1b (HEAD -> main) Add feature X
* a1b2c3d Fix bug Y
* e4f5g6h Initial commit
```

*Tip:* Use `git log --help` for more options and customization.


## 🕵️ 12. Viewing a Commit Exactly

Examine the details of a specific commit, including the changes it introduced. This helps in understanding the purpose and impact of a commit.

```sh
git show <commit-hash>
```

*Example:*

```sh
git show f3d2e1b
```

*Output:*

Displays the commit message, author, date, and the diff of changes made in that commit.


## 🔄 13. Unstaging Files

Remove files from the staging area without discarding their changes. This allows you to adjust which changes to include in the next commit.

```sh
git reset <file-name>
```

*Example:*

```sh
git reset README.md
```

*Note:* The changes remain in your working directory.


## ❌ 14. Discard Local Changes

Discard changes to files in your working directory, reverting them to the last committed version. **Use with caution**, as this will permanently remove your uncommitted changes.

- **Discard changes in a specific file:**

  ```sh
  git checkout -- <file-name>
  ```

  *Example:*

  ```sh
  git checkout -- README.md
  ```

- **Discard all local changes:**

  ```sh
  git reset --hard
  ```

  *Warning:* This command will revert all files to the last commit and cannot be undone.


## ⏪ 15. Restoring a File to an Earlier Version

Restore a file to a previous state from a specific commit or an earlier version. This is useful when you need to revert a file to how it was at a certain point in history.

- **Restore from a specific commit:**

  ```sh
  git checkout <commit-hash> -- <file-name>
  ```

  *Example:*

  ```sh
  git checkout f3d2e1b -- app.js
  ```

- **Using `git restore` (Git 2.23+):**

  ```sh
  git restore --source=<commit-hash> -- <file-name>
  ```

  *Example:*

  ```sh
  git restore --source=f3d2e1b -- app.js
  ```

*Tip:* After restoring, remember to stage and commit the changes if you want to keep them.



**Congratulations!** 🎉 You've now covered the essential concepts of creating snapshots in Git. By mastering these techniques, you'll be well-equipped to manage your project's version history effectively. 🚀

Regards,
**Muhammad Hashim** 👨‍💻
