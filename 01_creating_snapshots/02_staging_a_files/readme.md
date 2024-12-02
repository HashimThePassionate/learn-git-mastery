# 📂 Staging Files in Git

## 📑 Table of Contents

1. [**1. Create Files**](#-1-create-files) 📝
2. [**2. Check Status**](#-2-check-status) 🔍
3. [**3. Stage Files**](#-3-stage-files) ➕
4. [**4. Verify Staging**](#-4-verify-staging) ✔️
5. [**Summary**](#-summary) 📝


## 📝 1. Create Files

First, create the files you want to stage. For example, let's create two text files named `file1.txt` and `file2.txt`. 🖊️

```bash
echo hello > file1.txt
echo hello > file2.txt
```

*Example:*

```bash
echo hello > file1.txt
echo hello > file2.txt
```

*What This Does:*
- **`echo hello > file1.txt`**: Creates a file named `file1.txt` with the content `hello`.
- **`echo hello > file2.txt`**: Creates a file named `file2.txt` with the content `hello`.


## 🔍 2. Check Status

Check the status of your working directory and staging area using the `git status` command. This helps you understand which changes are staged, unstaged, or untracked. 📊

```bash
git status
```

*Example Output:*

```
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        file1.txt
        file2.txt
```

*Explanation:*
- **Untracked files**: Files that are not yet tracked by Git. They appear in red.


## ➕ 3. Stage Files

Stage the files you want to include in the next commit using the `git add` command. Staging allows you to prepare specific changes for a commit. 📦

```bash
git add *.txt       # Stage all .txt files in the directory
git add file1.txt   # Stage a specific file
git add .           # Stage all changes in the current directory
```

*Examples:*

1. **Stage All `.txt` Files:**

    ```bash
    git add *.txt
    ```

    *This command stages all files with the `.txt` extension in the current directory.*

2. **Stage a Specific File:**

    ```bash
    git add file1.txt
    ```

    *This command stages only `file1.txt`.*

3. **Stage All Changes:**

    ```bash
    git add .
    ```

    *This command stages all changes in the current directory, including new, modified, and deleted files.*

*Tip:* Use `git add -A` to stage all changes across the entire repository.


## ✔️ 4. Verify Staging

To verify that the files are staged, you can use `git status` again. This ensures that only the intended changes are prepared for the next commit. 🔍

```bash
git status
```

*Example Output:*

```
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   file1.txt
        new file:   file2.txt
```

*Explanation:*
- **Changes to be committed**: Files listed here are staged and ready to be committed. They appear in green.


## 📝 Summary

- **Create Files**: Use `echo` or your preferred method to create the files you want to stage.
- **Check Status**: Use `git status` to view the current state of your working directory and staging area.
- **Stage Files**: Use `git add` followed by the file name or pattern to stage specific files or all changes.
- **Verify Staging**: Use `git status` again to ensure that the correct files are staged for the next commit.


🎉 **Great Job!** 🎉 You've successfully learned how to stage files in your Git repository. Staging is a crucial step in managing your commits effectively, allowing you to control which changes are included in each snapshot of your project. 🚀

Regards,
**Muhammad Hashim** 👨‍💻
