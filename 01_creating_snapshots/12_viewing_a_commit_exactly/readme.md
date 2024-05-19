## Viewing a Commit Exactly

### Overview
This section explains how to view the exact changes made in a specific commit and examine the content of files within that commit using `git show` and related commands.

### Steps

1. **View Commit History**:
    ```bash
    git log --oneline
    ```
    - This command is used to view the commit history in a concise format.

2. **View Exact Content of a Commit**:
    ```bash
    git show <commit-id>
    ```
    - Replace `<commit-id>` with the unique identifier (e.g., commit hash) of the desired commit.
    ```bash
    git show 6973451
    ```
    - This command displays the exact changes made in the specified commit identified by `6973451`.

3. **View Content of a Commit Relative to HEAD**:
    ```bash
    git show HEAD~<number>
    ```
    - Replace `<number>` with the number of steps back from HEAD.
    ```bash
    git show HEAD~2
    ```
    - This command displays the changes made in the commit two steps back from the current HEAD.

4. **View Content of a Specific File in a Commit**:
    ```bash
    git show <commit-id>:<file-path>
    ```
    ```bash
    git show af7a9a4:.gitignore
    git show 01c9746:bin/app.bin
    ```
    - These commands show the content of `.gitignore` in commit `af7a9a4` and `bin/app.bin` in commit `01c9746`, respectively.

5. **List Files and Directories in a Commit**:
    ```bash
    git ls-tree HEAD~1
    ```
    - This command lists all files and directories in the commit one step back from the current HEAD.

6. **View Content of a Specific File in a Commit Using `ls-tree`**:
    ```bash
    git ls-tree HEAD~1:<file-path>
    ```
    - This command lists the content of the specified file in the commit one step back from the current HEAD.

---

By following these steps, you can precisely examine the content and changes made in a specific commit within your Git repository. If you have any questions or need further assistance, feel free to ask!