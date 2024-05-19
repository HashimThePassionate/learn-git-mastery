## Staging Files in Git

### 1. Create Files
First, create the files you want to stage. For example, let's create two text files named `file1.txt` and `file2.txt`.

```bash
echo hello > file1.txt
echo hello > file2.txt
```

### 2. Check Status
Check the status of your working directory and staging area using `git status`.

```bash
git status
```

### 3. Stage Files
Stage the files you want to include in the next commit using the `git add` command.

```bash
git add *.txt       # Stage all .txt files in the directory
git add file1.txt   # Stage a specific file
git add .           # Stage all changes in the current directory
```

### 4. Verify Staging
To verify that the files are staged, you can use `git status` again.

```bash
git status
```

### Summary
- Create the files you want to stage.
- Check the status of your working directory and staging area.
- Use `git add` to stage the files.
- Verify that the files are staged using `git status`.

---

By following these steps, you can stage files in your Git repository, preparing them for the next commit.