# Stashing

1. **Switching to the bugfix branch**: 
   ```bash
   git switch bugfix
   ```
   This command switches the current working branch to the `bugfix` branch.

2. **Making changes**: 
   ```bash
   echo Hello >> audience.txt
   ```
   This command appends "Hello" to the `audience.txt` file.

3. **Attempting to switch branches without committing changes**:
   ```bash
   git switch master
   ```
   This command fails because there are uncommitted changes in the `audience.txt` file. Git prevents switching branches to avoid overwriting these changes.

   Output:
   ```
   error: Your local changes to the following files would be overwritten by checkout:
        audience.txt
   Please commit your changes or stash them before you switch branches.
   Aborting
   ```

4. **Stashing changes**: 
   ```bash
   git stash push -m "New line Hello added in stash area"
   ```
   This command saves the current working directory and index state into a stash with a message. Stashing allows you to temporarily store changes without committing them.

   Output:
   ```
   Saved working directory and index state On bugfix: New line Hello added in stash area
   ```

5. **Creating a new file**:
   ```bash
   echo Hi > file.txt
   git status -S
   ```
   These commands create a new file named `file.txt` and check the status of the repository. The `file.txt` is listed as an untracked file.

6. **Stashing the new changes**:
   ```bash
   git stash -am "My new stash"
   ```
   This command saves the new untracked file into a stash with a message.

   Output:
   ```
   Saved working directory and index state On bugfix: My new stash
   ```

7. **Viewing the stash list**:
   ```bash
   git stash list
   ```
   This command lists all stashes, showing their reference names and messages.

   Output:
   ```
   stash@{0}: On bugfix: My new stash
   stash@{1}: On bugfix: New line Hello added in stash area
   ```

8. **Switching back to the master branch**:
   ```bash
   git switch master
   ```
   This command switches the current working branch to the `master` branch.

   Output:
   ```
   Switched to branch 'master'
   ```

9. **Applying a specific stash to the staging area**:
   ```bash
   git stash show 1
   ```
   This command shows the changes in the specified stash number.

   Output:
   ```
   audience.txt | 2 +-
   1 file changed, 1 insertion(+), 1 deletion(-)
   ```

10. **Applying the stash to the working directory**:
    ```bash
    git stash apply 1
    ```
    This command applies the changes stored in the specified stash to the working directory.

    Output:
    ```
    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git restore <file>..." to discard changes in working directory)
            modified:   audience.txt
    no changes added to commit (use "git add" and/or "git commit -a")
    ```

11. **Dropping a specific stash**:
    ```bash
    git stash drop 1
    ```
    This command removes the specified stash from the stash list.

    Output:
    ```
    Dropped refs/stash@{1} (a28d97d5c3c0a857f32b0e312cbf0213a236e19e)
    ```

12. **Clearing all stashes**:
    ```bash
    git stash clear
    ```
    This command removes all stashes from the stash list.

These commands demonstrate how to stash changes, list stashes, apply stashes, and clear stashes in Git. Stashing is useful when you need to temporarily store changes without committing them.