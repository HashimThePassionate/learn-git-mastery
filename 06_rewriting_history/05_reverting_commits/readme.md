### Why Use `git revert` Instead of `git reset --hard` on a Remote Repository

Using `git revert` instead of `git reset --hard` on a remote repository is essential for maintaining a collaborative and stable environment. Here’s why:

1. **Preservation of History**: `git revert` creates a new commit that undoes the changes introduced by previous commits without altering the commit history. This maintains a clear and traceable history of all changes made to the repository.

2. **Avoiding Disruption**: `git reset --hard` rewrites the commit history, which can disrupt the work of other collaborators. When others have based their work on the commit history you are rewriting, it causes conflicts and confusion.

3. **Safe Collaboration**: In a shared repository, `git revert` ensures that everyone has a consistent view of the project’s history. It avoids the need for force-pushing changes, which can overwrite other people’s work.

### Explanation of Steps Using `git revert`

Here’s a detailed explanation of how to use `git revert` to undo changes while keeping the repository history intact, based on your example:

1. **View the Commit History:**
   ```sh
   git log --oneline --all --graph
   ```
   ```
   * f666091 (HEAD -> master) WIP
   * 111bd75 Update terms of service and Google Map SDK version.
   * 72856ea WIP
   * 8441b05 Add a reference to Google Map SDK.
   * 8527033 Change the color of restaurant icons.
   * af26a96 Fix a typo.
   * 6fb2ba7 Render restaurants the map.
   * 70ef834 Initial commit
   ```

2. **Revert the Last Three Commits:**
   ```sh
   git revert --no-commit HEAD~3..
   ```
   - This command prepares the repository to revert the changes made by the last three commits but does not create the revert commit yet.
   - You are now in a state where the changes are undone in your working directory, and you need to continue the revert process.

3. **Check the Status:**
   ```sh
   git status -s
   ```
   ```
   M  map.txt    
   M  package.txt
   D  terms.txt
   ```
   - These are the changes that will be included in the revert commit.

4. **Continue the Revert Process:**
   ```sh
   git revert --continue
   ```
   - This completes the revert operation by creating a new commit that undoes the changes introduced by the specified commits.

5. **View the Updated Commit History:**
   ```sh
   git log --oneline --all --graph
   ```
   ```
   * 0cd0b85 (HEAD -> master) Reverting bad code
   * f666091 WIP
   * 111bd75 Update terms of service and Google Map SDK version.
   * 72856ea WIP
   * 8441b05 Add a reference to Google Map SDK.
   * 8527033 Change the color of restaurant icons.
   * af26a96 Fix a typo.
   * 6fb2ba7 Render restaurants the map.
   * 70ef834 Initial commit
   ```
   - The new commit `0cd0b85` documents the reversal of the changes, keeping the history intact and clear.

### Summary

Using `git revert` is crucial in a collaborative environment as it safely undoes changes by creating new commits, thereby preserving the commit history and avoiding disruptions for other contributors. This method ensures that everyone working on the project has a consistent and stable view of the repository’s history, promoting a smooth and effective collaboration process.