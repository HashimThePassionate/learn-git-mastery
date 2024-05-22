## Viewing merged and unmerged branches:

1. **Viewing Merged Branches:**

    Command:
    ```bash
    git branch --merged
    ```

    Output:
    ```plaintext
      bugfix/about
      feature/password
    * master
    ```

    Explanation:
    This command lists all branches that have been merged into the current branch (`master` in this case). The branches `bugfix/about` and `feature/password` have been merged into `master`.

2. **Deleting Merged Branches:**

    Commands:
    ```bash
    git branch -d bugfix/about
    git branch -d feature/password
    ```

    Explanation:
    - `git branch -d bugfix/about`: Deletes the `bugfix/about` branch since it has already been merged into `master`.
    - `git branch -d feature/password`: Deletes the `feature/password` branch since it has already been merged into `master`.

3. **Viewing Unmerged Branches:**

    Command:
    ```bash
    git branch --no-merged
    ```

    Explanation:
    This command lists all branches that have not been merged into the current branch (`master` in this case). Since there are no branches listed, it means all branches have been merged into `master`.