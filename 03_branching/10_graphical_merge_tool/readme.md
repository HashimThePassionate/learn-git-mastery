# Graphical merge tool:

1. **Creating and Making Changes in Bugfix Branch:**

    Commands:
    ```bash
    git switch -C bugfix
    code audience.txt  # Assuming this opens the file in an editor
    ```

    Explanation:
    This creates a new branch named `bugfix` and opens the `audience.txt` file for editing. Assuming you've added "This is bugfix" to `audience.txt`.

2. **Staging Changes in Bugfix Branch:**

    Commands:
    ```bash
    git add .
    git commit -m "Bugfix"
    ```

    Explanation:
    - `git add .`: Stages all changes.
    - `git commit -m "Bugfix"`: Commits the changes to the `bugfix` branch.

3. **Switching Back to Master and Making Changes:**

    Commands:
    ```bash
    git switch master
    code audience.txt  # Assuming this opens the file in an editor
    ```

    Explanation:
    This switches back to the `master` branch and opens the `audience.txt` file for editing. Assuming you've added "This is master" to `audience.txt`.

4. **Staging Changes in Master Branch:**

    Commands:
    ```bash
    git add .
    git commit -m "master"
    ```

    Explanation:
    - `git add .`: Stages all changes.
    - `git commit -m "master"`: Commits the changes to the `master` branch.

5. **Merging Master into Bugfix Branch:**

    Command:
    ```bash
    git merge master
    ```

    Explanation:
    This merges the changes from the `master` branch into the `bugfix` branch.

6. **Setting Up P4Merge as the Default Graphical Merge Tool:**

    Commands:
    ```bash
    git config --global merge.tool p4merge
    git config --global mergetool.p4merge.path "C:\Program Files\Perforce\p4merge"
    ```

    Explanation:
    - `git config --global merge.tool p4merge`: Sets P4Merge as the default merge tool globally.
    - `git config --global mergetool.p4merge.path "C:\Program Files\Perforce\p4merge"`: Specifies the path to the P4Merge executable.

7. **Using P4Merge to Resolve Merge Conflict:**

    Explanation:
    After configuring P4Merge, when you encounter a merge conflict and run `git mergetool`, Git will launch P4Merge, allowing you to resolve the conflicts graphically.