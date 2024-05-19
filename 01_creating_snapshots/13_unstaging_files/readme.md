## Unstaging Files

### Overview
This section explains how to undo staging changes and restore files to the unstaged state using the `git restore --staged` command.

### Steps

1. **Make Changes to a File**:
    ```bash
    echo fishes >> moon/main.js
    ```
    - This command appends or modifies the content of `moon/main.js`.

2. **Add Changes to Staging Area**:
    ```bash
    git add moon/main.js
    ```
    - This command adds the modified changes to the staging area.

3. **Undo Staging Changes**:
    ```bash
    git restore --staged moon/main.js
    ```
    - This command restores the changes in `moon/main.js` from the staging area to the unstaged state.

---

By following these steps, you can easily undo staging changes and revert files back to the unstaged state in your Git repository. If you have any questions or need further assistance, feel free to ask!