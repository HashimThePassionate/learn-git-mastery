# Three way merges

1. **Viewing Commits Graphically:**

    Command:
    ```bash
    git log --oneline --all --graph
    ```

    Output:
    ```plaintext
    *   d48d735 (HEAD -> master) Merge branch 'bugfix/about'
    |\
    | * c34c6bb (bugfix/about) Updated toc
    |/
    * b07884d Added new changes
    * a642e12 Add header to all pages.
    * ... (other commits)
    ```

    Explanation:
    This command displays a graphical representation of all commits, showing the branches and their relationships.

2. **Creating and Making Changes in Feature Branch:**

    Commands:
    ```bash
    git switch -C feature/password
    echo "***********" > password.txt
    git add .
    git commit -m "Password Feature Added"
    git log --oneline --all --graph
    ```

    Output:
    ```plaintext
    * d203fc8 (HEAD -> feature/password) Password Feature Added
    *   d48d735 (master) Merge branch 'bugfix/about'
    |\
    | * c34c6bb (bugfix/about) Updated toc
    |/
    * b07884d Added new changes
    * a642e12 Add header to all pages.
    * ... (other commits)
    ```

    Explanation:
    - `git switch -C feature/password`: Creates a new branch named `feature/password` and switches to it.
    - `echo "***********" > password.txt`, `git add .`, `git commit -m "Password Feature Added"`: Adds and commits changes to `password.txt`.

3. **Switching Back to Master and Making Changes:**

    Commands:
    ```bash
    git switch master
    echo "Hello" >> objectives.txt
    git add .
    git commit -m "Updated objective.txt"
    git log --oneline --all --graph
    ```

    Output:
    ```plaintext
    * 2902f6f (HEAD -> master) Updated objective.txt
    | * d203fc8 (feature/password) Password Feature Added
    |/
    *   d48d735 Merge branch 'bugfix/about'
    |\
    | * c34c6bb (bugfix/about) Updated toc
    |/
    * b07884d Added new changes
    * a642e12 Add header to all pages.
    * ... (other commits)
    ```

    Explanation:
    - `git switch master`: Switches back to the `master` branch.
    - `echo "Hello" >> objectives.txt`, `git add .`, `git commit -m "Updated objective.txt"`: Adds and commits changes to `objectives.txt`.

4. **Merging Feature Branch into Master:**

    Commands:
    ```bash
    git merge feature/password
    ```

    Output:
    ```plaintext
    Auto-merging objectives.txt
    CONFLICT (content): Merge conflict in objectives.txt
    Automatic merge failed; fix conflicts and then commit the result.
    ```

    Explanation:
    A merge conflict occurred because changes were made to the same file (`objectives.txt`) on both branches (`master` and `feature/password`).

5. **Resolving Merge Conflict:**

    Explanation:
    To resolve the conflict, you would open the conflicted file (`objectives.txt`) in your text editor, manually resolve the conflicting lines, save the changes, and then add and commit the resolved file.

6. **Viewing Commits Graphically After Merge Conflict:**

    Command:
    ```bash
    git log --oneline --all --graph
    ```

    Output:
    ```plaintext
    *   1e98cf0 (HEAD -> master) Merge branch 'feature/password'
    |\
    | * d203fc8 (feature/password) Password Feature Added
    * | 2902f6f Updated objective.txt
    | * d48d735 Merge branch 'bugfix/about'
    |\
    | * c34c6bb (bugfix/about) Updated toc
    |/
    * b07884d Added new changes
    * a642e12 Add header to all pages.
    * ... (other commits)
    ```

    Explanation:
    The graph now shows the merge commit (`1e98cf0`) where the `feature/password` branch was merged into `master`, along with other commits.