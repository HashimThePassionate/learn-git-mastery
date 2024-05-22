### Why Use `git commit --amend`?

Amending the last commit in Git is a useful technique for making corrections or additions to your most recent commit without creating a new commit. This is particularly helpful for:

- Correcting mistakes in the last commit message.
- Adding or removing changes from the last commit.
- Avoiding cluttering the commit history with multiple minor fix commits.

Here’s a step-by-step explanation of using `git commit --amend` and how it was applied in your example:

### Step-by-Step Explanation

1. **Initial State: View the Commit History**
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

2. **Make Changes to a File:**
   ```sh
   echo cafes >> map.txt
   ```

3. **Check the Status of Changes:**
   ```sh
   git status -s
   ```
   Output:
   ```
    M map.txt
   ```

4. **Stage and Commit the Changes:**
   ```sh
   git commit -am "Render cafes on the map"
   ```
   Output:
   ```
   [master f8b5d10] Render cafes on the map
   1 file changed, 1 insertion(+)
   ```

5. **View the Updated Commit History:**
   ```sh
   git log --oneline --all --graph
   ```
   Output:
   ```
   * f8b5d10 (HEAD -> master) Render cafes on the map
   * 0cd0b85 Reverting bad code
   * f666091 WIP
   * 111bd75 Update terms of service and Google Map SDK version.
   * 72856ea WIP
   * 8441b05 Add a reference to Google Map SDK.
   * 8527033 Change the color of restaurant icons.
   * af26a96 Fix a typo.
   * 6fb2ba7 Render restaurants the map.
   * 70ef834 Initial commit
   ```

6. **Make Additional Changes to the Same File:**
   ```sh
   echo >> map.txt
   echo blue >> map.txt
   ```

7. **Stage the New Changes:**
   ```sh
   git add .
   ```
   
8. **Amend the Previous Commit with the New Changes:**
   ```sh
   git commit --amend
   ```
   Output:
   ```
   [master d3e877e] Render cafes on the map
   Date: Sun May 19 22:05:25 2024 +0500
   1 file changed, 2 insertions(+)
   ```

9. **Verify the Amended Commit:**
   ```sh
   git log --oneline --all
   ```
   Output:
   ```
   d3e877e (HEAD -> master) Render cafes on the map
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

10. **Make Additional Changes and Stage Them:**
    ```sh
    echo Hello > file1.txt
    git add .
    ```

11. **Amend the Commit Again with the New Changes:**
    ```sh
    git commit --amend
    ```
    Output:
    ```
    [master 6843550] Render cafes on the map
    Date: Sun May 19 22:05:25 2024 +0500
    2 files changed, 3 insertions(+)
    create mode 100644 file1.txt
    ```

12. **View the Final Commit History:**
    ```sh
    git log --oneline --all
    ```
    Output:
    ```
    6843550 (HEAD -> master) Render cafes on the map
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

### Summary

The `git commit --amend` command is a powerful tool for refining the last commit. It allows you to correct mistakes or include additional changes, keeping your commit history clean and meaningful. In your example, you used it to update the commit with additional changes to `map.txt` and the creation of `file1.txt`, ensuring all related changes are captured in a single, cohesive commit.