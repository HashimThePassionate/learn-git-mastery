To squash commits, you follow a similar process to reordering commits with an interactive rebase:

1. **View the Commit History:**
   ```sh
   git log --oneline
   ```
   Output:
   ```
   a0fad60 (HEAD -> master) Render cafes on the maps
   fd4b3f4 Update terms of service and Google Map SDK version.
   8fc2741 Change the color of restaurant icons.
   146c49c Fix a typo.
   1e4ffcc Render restaurants on the map.
   944a2ca Add a reference to Google Map SDK.
   70ef834 Initial commit
   ```

2. **Initiate an Interactive Rebase to Squash Commits:**
   ```sh
   git rebase -i 944a2ca^
   ```
   This command opens an editor with a list of commits.

3. **In the Editor:**
   - Mark the commits you want to squash with "squash" or "s".
   - Save and close the editor.

4. **Edit the Commit Message (if necessary):**
   After marking the commits for squashing, Git will open another editor to allow you to edit the commit message for the squashed commit.

5. **Continue the Rebase Process:**
   After saving the changes in the editor, Git will automatically continue the rebase process.

6. **View the Updated Commit History:**
   ```sh
   git log --oneline
   ```
   Output:
   ```
   a39da7e (HEAD -> master) Render cafes on the maps
   5287c8c Update terms of service and Google Map SDK version.
   c432f2c Render restaurants on the map.
   944a2ca Add a reference to Google Map SDK.
   70ef834 Initial commit
   ```

After completing these steps, the specified commits were squashed into a single commit, and the commit history was updated accordingly.