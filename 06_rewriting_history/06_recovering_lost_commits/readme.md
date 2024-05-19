### Recovering Lost Commits with Git Reflog

When you perform a hard reset, it might seem like you’ve permanently lost commits. However, Git keeps a record of all changes to the HEAD pointer in the reflog, allowing you to recover those commits. Here’s an explanation of the process you followed to recover lost commits using `git reflog`.

### Steps Explained

1. **View the Current Commit History:**
   ```sh
   git log --oneline --all --graph
   ```
   Output:
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

   This shows the current state of your repository, with the latest commit being `0cd0b85` (Reverting bad code).

2. **Perform a Hard Reset:**
   ```sh
   git reset --hard HEAD~6
   ```
   - This command resets the HEAD to the commit six commits back from the current HEAD.
   - It removes the latest six commits from the history.

3. **View the Updated Commit History:**
   ```sh
   git log --oneline --all --graph
   ```
   Output:
   ```
   * af26a96 (HEAD -> master) Fix a typo.
   * 6fb2ba7 Render restaurants the map.
   * 70ef834 Initial commit
   ```

   The commit history now only shows the first three commits, indicating that the latest six commits have been removed.

4. **View the Reflog:**
   ```sh
   git reflog
   ```
   Output:
   ```
   af26a96 (HEAD -> master) HEAD@{0}: reset: moving to HEAD~6
   0cd0b85 HEAD@{1}: commit: Reverting bad code
   f666091 HEAD@{2}: reset: moving to f666091b6691ed523dc80af32e900c365e434c24
   f666091 HEAD@{3}: reset: moving to HEAD
   f666091 HEAD@{4}: reset: moving to HEAD
   f666091 HEAD@{5}: reset: moving to HEAD~1
   088455d HEAD@{6}: commit: .
   f666091 HEAD@{7}: commit: WIP
   111bd75 HEAD@{8}: commit: Update terms of service and Google Map SDK version.
   72856ea HEAD@{9}: commit: WIP
   8441b05 HEAD@{10}: commit: Add a reference to Google Map SDK.
   8527033 HEAD@{11}: commit: Change the color of restaurant icons.
   af26a96 (HEAD -> master) HEAD@{12}: commit: Fix a typo.
   6fb2ba7 HEAD@{13}: commit: Render restaurants the map.
   70ef834 HEAD@{14}: commit (initial): Initial commit
   ```

   The reflog shows a record of all changes to the HEAD pointer. Each entry indicates the previous position of HEAD, allowing you to recover lost commits.

5. **Recover the Lost Commits:**
   ```sh
   git reset --hard HEAD@{1}
   ```
   - This command moves the HEAD back to the state it was in at `HEAD@{1}`, which corresponds to the commit `0cd0b85` (Reverting bad code).

6. **Verify the Commit History:**
   ```sh
   git log --oneline --all --graph
   ```
   Output:
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

   The commit history is now restored to its previous state, including all the commits that were "lost" due to the hard reset.

### Summary

By using the reflog, you can recover lost commits even after performing operations like `git reset --hard`. The reflog tracks all movements of the HEAD pointer, allowing you to identify and restore previous states of your repository. This ensures that no commit is ever truly lost, providing a safety net for repository management.