To reword commit messages using an interactive rebase, you followed these steps:

1. **View the Commit History:**
   ```sh
   git log --oneline
   ```
   Output:
   ```
   528758b (HEAD -> master) Render cafes on the maps
   453f9e0 Update terms of service and Google Map SDK version.
   3fdac0a Add a reference to Google Map SDK.
   8527033 Change the color of restaurant icons.
   af26a96 Fix a typo.
   6fb2ba7 Render restaurants the map.
   70ef834 Initial commit
   ```

2. **Initiate an Interactive Rebase to Reword Commit Messages:**
   ```sh
   git rebase -i 6fb2ba7^
   ```
   This command opens an editor with a list of commits.

3. **In the Editor:**
   - Change `pick` to `reword` for the commits you want to reword.
   - Save and close the editor.

4. **Reword the Commit Message:**
   In this step, you modified the commit message for the commit `6fb2ba7` to "Render restaurants on the map."

5. **Continue the Rebase Process:**
   After saving the changes in the editor, Git automatically continues the rebase process.

6. **View the Updated Commit History:**
   ```sh
   git log --oneline
   ```
   Output:
   ```
   4d7aa04 (HEAD -> master) Render cafes on the maps
   eaf37d5 Update terms of service and Google Map SDK version.
   37e6289 Add a reference to Google Map SDK.
   157d968 Change the color of restaurant icons.
   12e3f9c Fix a typo.
   bd6b847 Render restaurants on the map.
   70ef834 Initial commit
   ```

After completing these steps, the commit message for the specified commit (`6fb2ba7`) was successfully reworded.