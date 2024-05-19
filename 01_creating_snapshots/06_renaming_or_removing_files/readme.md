## Renaming or Moving Files in Git

### 1. Rename or Move File Using Standard Unix Command
Use the `mv` command to rename or move a file in your working directory. For example, let's rename `file1.txt` to `main.js`.

```bash
mv file1.txt main.js
```

### 2. Check Status
Check the status of your repository to see the changes made by the `mv` command.

```bash
git status
```

### 3. Stage Renamed File
Stage the renamed file (`main.js`) using the `git add` command.

```bash
git add main.js
```

### Using `git mv` Command (Optional)
Alternatively, you can use the `git mv` command to rename or move a file in your repository. This command will both rename the file in your working directory and stage the change in one step.

```bash
git mv main.js file1.txt
```

### Summary
- Use the standard Unix command `mv` to rename or move a file in your working directory.
- Stage the renamed or moved file using `git add`.
- Optionally, use the `git mv` command to rename or move a file in your repository in one step.

By following these steps, you can effectively rename or move files in your Git repository.