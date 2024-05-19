To reorder commits using an interactive rebase, here's what you did:

1. **View the Commit History:**
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

2. **Initiate an Interactive Rebase to Reorder Commits:**
   ```sh
   git rebase -i 70ef834
   ```
   This command opens an editor with a list of commits.

3. **In the Editor:**
   - Reorder the commits as desired by changing their order in the list.
   - Save and close the editor.

4. **Continue the Rebase Process:**
   After saving the changes in the editor, Git automatically continues the rebase process.

5. **View the Updated Commit History:**
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

After completing these steps, the commits were successfully reordered according to your specifications.