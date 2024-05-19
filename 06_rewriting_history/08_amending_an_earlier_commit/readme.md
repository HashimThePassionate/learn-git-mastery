### Step-by-Step Explanation:

1. **View the Commit History:**
   ```sh
   git log --oneline
   ```
   Output:
   ```
   46d4118 (HEAD -> master) Render cafes on the maps
   0cd0b85 Reverting bad code
   f666091 WIP
   111bd75 Update terms of service and Google Map SDK version.
   72856ea WIP
   8441b05 Add a reference to Google Map SDK.
   8527033 Change the color of restaurant icons.
   af26a96 Fix a typo.
   6fb2ba7 Render restaurants the map.
   70ef834 Initial commit
   ```

2. **View Details of a Specific Commit:**
   ```sh
   git show 8441b05
   ```
   Output:
   ```
   commit 8441b059eda5262f08f8030e383a72256adc8bd7 
   Author: Moshfegh Hamedani <moshfegh@live.com.au>
   Date:   Wed Sep 9 17:41:49 2020 -0700

   Add a reference to Google Map SDK.

   diff --git a/package.txt b/package.txt
   new file mode 100644
   index 0000000..7324ece
   --- /dev/null
   +++ b/package.txt
   @@ -0,0 +1 @@
   +Google Map 1.0.0
   ```

3. **Initiate an Interactive Rebase:**
   ```sh
   git rebase -i 8527033
   ```
   Output:
   ```
   Stopped at 8441b05...  Add a reference to Google Map SDK.
   You can amend the commit now, with

     git commit --amend

   Once you are satisfied with your changes, run

     git rebase --continue
   ```

4. **Create a New File and Check Status:**
   ```sh
   echo license > license.txt
   git status -s
   ```
   Output:
   ```
   ?? license.txt
   ```

5. **Stage and Amend the Commit:**
   ```sh
   git add .
   git commit --amend
   ```
   Output:
   ```
   [detached HEAD 3fdac0a] Add a reference to Google Map SDK.
    Author: Moshfegh Hamedani <moshfegh@live.com.au>
    Date: Wed Sep 9 17:41:49 2020 -0700
    2 files changed, 2 insertions(+)
    create mode 100644 license.txt
    create mode 100644 package.txt
   ```

6. **Continue the Rebase Process:**
   ```sh
   git rebase --continue
   ```
   Output:
   ```
   Successfully rebased and updated refs/heads/master.
   ```

7. **View the Updated Commit History:**
   ```sh
   git log --oneline --all --graph
   ```
   Output:
   ```
   * 491c434 (HEAD -> master) Render cafes on the maps
   * 244097d Reverting bad code
   * 4cfdcdf WIP
   * d3ee50e Update terms of service and Google Map SDK version.
   * 559ca3d WIP
   * 3fdac0a Add a reference to Google Map SDK.
   * 8527033 Change the color of restaurant icons.
   * af26a96 Fix a typo.
   * 6fb2ba7 Render restaurants the map.
   * 70ef834 Initial commit
   ```

8. **View Details of the Amended Commit:**
   ```sh
   git show 3fdac0a
   ```
   Output:
   ```
   commit 3fdac0a8c0c36d1dc11acaa5dfa1590cd43163ce
   Author: Moshfegh Hamedani <moshfegh@live.com.au>
   Date:   Wed Sep 9 17:41:49 2020 -0700

   Add a reference to Google Map SDK.

   diff --git a/license.txt b/license.txt
   new file mode 100644
   index 0000000..cdc5d66
   --- /dev/null
   +++ b/license.txt
   @@ -0,0 +1 @@
   +license
   diff --git a/package.txt b/package.txt
   new file mode 100644
   index 0000000..7324ece
   --- /dev/null
   +++ b/package.txt
   @@ -0,0 +1 @@
   +Google Map 1.0.0
   ```

### Summary:

In summary, you initiated an interactive rebase to edit an earlier commit (`Add a reference to Google Map SDK.`). Then you amended that commit by adding a new file (`license.txt`). Finally, you continued the rebase process to update the commit history.