# Fast Forward Merge

1. **Viewing Commits Graphically:**
   
    Command:
    ```bash
    git log --oneline --all --graph
    ```

    Output:
    ```plaintext
    * b07884d (bugfix) Added new changes
    * a642e12 (HEAD -> master) Add header to all pages.
    * 50db987 Include the first section in TOC.
    * 555b62e Include the note about committing after staging the changes.
    * 91f7d40 Explain various ways to stage changes.
    * edb3594 First draft of staging changes.
    * 24e86ee Add command line and GUI tools to the objectives.
    * 36cd6db Include the command prompt in code sample.
    * 9b6ebfd Add a header to the page about initializing a repo.
    * fa1b75e Include the warning about removing .git directory.
    * dad47ed Write the first draft of initializing a repo.
    * fb0d184 Define the audience.
    * 1ebb7a7 Define the object
    ```

    Explanation:
    This command displays a graphical representation of all commits, showing the branches and their relationships.

2. **Fast Forward Merge to Master:**

    Commands:
    ```bash
    git switch master
    git merge bugfix
    ```

    Output:
    ```plaintext
    Updating a642e12..b07884d
    Fast-forward
     audience.txt | 4 +++-
     1 file changed, 3 insertions(+), 1 deletion(-)
    ```

    Explanation:
    - `git switch master`: Switches to the `master` branch.
    - `git merge bugfix`: Merges the `bugfix` branch into `master` with a fast-forward merge since there is a linear path from the current `master` commit to the `bugfix` commit.

3. **Viewing Commits Graphically After Fast Forward Merge:**

    Command:
    ```bash
    git log --oneline --all --graph
    ```

    Output:
    ```plaintext
    * b07884d (HEAD -> master, bugfix) Added new changes
    * a642e12 Add header to all pages.
    * 50db987 Include the first section in TOC.
    * 555b62e Include the note about committing after staging the changes.
    * 91f7d40 Explain various ways to stage changes.
    * edb3594 First draft of staging changes.
    * 24e86ee Add command line and GUI tools to the objectives.
    * 36cd6db Include the command prompt in code sample.
    * 9b6ebfd Add a header to the page about initializing a repo.
    * fa1b75e Include the warning about removing .git directory.
    * dad47ed Write the first draft of initializing a repo.
    * fb0d184 Define the audience.
    * 1ebb7a7 Define the objectives.
    * ca49180 Initial commit.
    ```

    Explanation:
    After the merge, the `master` branch now points to the same commit as `bugfix`, as shown in the graph.

4. **Creating a New Branch and Making Changes:**

    Commands:
    ```bash
    git branch -d bugfix
    git switch -C bugfix/about
    git add audience.txt
    git commit -m "Updated audience file"
    git switch master
    ```

    Output:
    ```plaintext
    Switched to a new branch 'bugfix/about'
    ```

    Explanation:
    - `git branch -d bugfix`: Deletes the `bugfix` branch.
    - `git switch -C bugfix/about`: Creates a new branch named `bugfix/about` and switches to it.
    - `git add audience.txt` and `git commit -m "Updated audience file"`: Stages and commits changes to `audience.txt`.
    - `git switch master`: Switches back to the `master` branch.

5. **Viewing Commits Graphically After Creating and Switching to New Branch:**

    Command:
    ```bash
    git log --oneline --all --graph
    ```

    Output:
    ```plaintext
    * c34c6bb (bugfix/about) Updated toc
    * b07884d (HEAD -> master) Added new changes
    * a642e12 Add header to all pages.
    * ... (other commits)
    ```

    Explanation:
    The `bugfix/about` branch is now ahead of `master` due to the new commit.

6. **Merging Branch Without Fast Forward:**

    Commands:
    ```bash
    git merge --no-ff bugfix/about
    ```

    Output:
    ```plaintext
    Merge made by the 'ort' strategy.
     audience.txt | 5 ++++-
     1 file changed, 4 insertions(+), 1 deletion(-)
    ```

    Explanation:
    This command merges the `bugfix/about` branch into `master` with a merge commit, not a fast-forward merge.

7. **Viewing Commits Graphically After Merge:**

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
    The graph now shows a merge commit, indicating the merge of `bugfix/about` into `master`.

8. **Disabling Fast Forward Merge:**

    Commands:
    ```bash
    git config ff no
    git config --global ff no
    ```

    Explanation:
    These commands configure Git to disable fast-forward merges either for the current repository or globally for all repositories.