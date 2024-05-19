Here's a detailed explanation of the steps you took to split a commit into two separate commits:

### Initial State

You started with the following commit history:
```sh
git log --oneline --all --graph
* a39da7e (HEAD -> master) Render cafes on the maps
* 5287c8c Update terms of service and Google Map SDK version.
* c432f2c Render restaurants on the map.
* 944a2ca Add a reference to Google Map SDK.
* 70ef834 Initial commit
```

### Starting the Rebase

1. **Initiate an Interactive Rebase:**
   ```sh
   git rebase -i 5287c8c^
   ```
   This command opens an editor for an interactive rebase starting from the commit before `5287c8c`.

2. **Stop at the Commit to Split:**
   The interactive rebase stopped at the commit `5287c8c` and you were prompted to amend the commit:
   ```sh
   Stopped at 5287c8c...  Update terms of service and Google Map SDK version.
   You can amend the commit now, with
   git commit --amend
   Once you are satisfied with your changes, run
   ```

### Splitting the Commit

3. **Reset to Unstage Changes:**
   ```sh
   git reset --mixed HEAD^
   ```
   This command unstages the changes from the commit `5287c8c` but keeps them in the working directory.

4. **Check the Status:**
   ```sh
   git status -s
   ```
   Output:
   ```sh
    M package.txt
   ?? terms.txt
   ```

5. **Stage and Commit the First Change:**
   ```sh
   git add package.txt
   git commit -m "Update Google Map SDK version 1.0 => 2.0"
   ```
   This creates a new commit `e3e0263` with the changes to `package.txt`.

6. **Check the Commit History:**
   ```sh
   git log --oneline --all --graph
   ```
   Output:
   ```sh
   * e3e0263 (HEAD) Update Google Map SDK version 1.0 => 2.0
   | * a39da7e (master) Render cafes on the maps
   | * 5287c8c Update terms of service and Google Map SDK version.
   |/
   * c432f2c Render restaurants on the map.
   * 944a2ca Add a reference to Google Map SDK.
   * 70ef834 Initial commit
   ```

7. **Stage and Commit the Second Change:**
   ```sh
   git add terms.txt
   git commit -m "Add terms of services"
   ```
   This creates another new commit `56e3b7a` with the changes to `terms.txt`.

8. **Check the Commit History Again:**
   ```sh
   git log --oneline --all --graph
   ```
   Output:
   ```sh
   * 56e3b7a (HEAD) Add terms of services
   * e3e0263 Update Google Map SDK version 1.0 => 2.0
   | * a39da7e (master) Render cafes on the maps
   | * 5287c8c Update terms of service and Google Map SDK version.
   |/
   * c432f2c Render restaurants on the map.
   * 944a2ca Add a reference to Google Map SDK.
   * 70ef834 Initial commit
   ```

### Completing the Rebase

9. **Continue the Rebase:**
   ```sh
   git rebase --continue
   ```
   This completes the rebase process and updates the commit history on the `master` branch.

10. **Final Commit History:**
    ```sh
    git log --oneline --all --graph
    ```
    Output:
    ```sh
    * 08e5382 (HEAD -> master) Render cafes on the maps
    * 56e3b7a Add terms of services
    * e3e0263 Update Google Map SDK version 1.0 => 2.0
    * c432f2c Render restaurants on the map
    * 944a2ca Add a reference to Google Map SDK
    * 70ef834 Initial commit
    ```

By following these steps, you successfully split the original commit `5287c8c` into two separate commits: `e3e0263` (updating the SDK version) and `56e3b7a` (adding the terms of service).