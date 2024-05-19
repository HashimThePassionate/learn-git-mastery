## Discard Local Changes and Remove Untracked Files

### Overview
This section explains how to discard local changes made to tracked files and remove untracked files from your Git repository using `git restore` and `git clean` commands.

### Steps

1. **Discard Local Changes to a Tracked File**:
    ```bash
    echo Programming >> moon/main.js
    ```
    - This command modifies the content of `moon/main.js`.

    ```bash
    git restore moon/main.js
    ```
    - This command restores the last committed version of `moon/main.js`, discarding the local changes.

2. **Create a New File and Write Content**:
    ```bash
    echo Hello > moon/file3.js
    ```
    - This command creates a new file `file3.js` inside the `moon` directory and writes "Hello" to it.

3. **Check Status for Untracked Files**:
    ```bash
    git status -s
    ```
    - This command displays the untracked file `file3.js` in the repository.

4. **Remove Untracked File Completely**:
    ```bash
    git clean -h
    ```
    - This command displays help information for the `git clean` command.

    ```bash
    git clean --force file3.js
    ```
    - This command removes the untracked file `file3.js` from the repository forcefully.

---

By following these steps, you can discard local changes to tracked files and remove untracked files from your Git repository as needed. If you have any questions or need further assistance, feel free to ask!