### Understanding `git reset`: Soft, Mixed, and Hard

The `git reset` command is used to undo changes in your Git repository. It can move the HEAD pointer and reset the state of your working directory and staging area. There are three modes of `git reset`: soft, mixed, and hard. Here’s an explanation of each, using your example as a guide.

#### 1. Soft Reset (`--soft`)

**Purpose:** Moves the HEAD to a specific commit and leaves the changes staged (in the index).

**Scenario:**
- You want to undo a commit but keep the changes staged for the next commit.

**Example Steps:**

1. **Current Commit History:**
   ```
   * 088455d (HEAD -> master) .
   * f666091 WIP
   * 111bd75 Update terms of service and Google Map SDK version.
   ```

2. **Execute Soft Reset:**
   ```sh
   git reset --soft HEAD~1
   ```

3. **Result:**
   - The commit `088455d` is undone.
   - Changes from `088455d` are staged.
   - HEAD points to `f666091`.
   
4. **Verify Changes:**
   ```sh
   git status -s
   ```
   ```
   M  terms.txt
   ```

   The changes in `terms.txt` are staged but not committed.

#### 2. Mixed Reset (`--mixed`)

**Purpose:** Moves the HEAD to a specific commit and unstages the changes (keeps them in the working directory).

**Scenario:**
- You want to undo a commit and unstage the changes, but keep the changes in the working directory.

**Example Steps:**

1. **Current Commit History:**
   ```
   * f666091 (HEAD -> master) WIP
   * 111bd75 Update terms of service and Google Map SDK version.
   ```

2. **Execute Mixed Reset:**
   ```sh
   git reset --mixed HEAD
   ```

3. **Result:**
   - The commit `088455d` is undone.
   - Changes from `088455d` are unstaged.
   - HEAD points to `f666091`.

4. **Verify Changes:**
   ```sh
   git status -s
   ```
   ```
    M terms.txt
   ```
   The changes in `terms.txt` are in the working directory but not staged.

#### 3. Hard Reset (`--hard`)

**Purpose:** Moves the HEAD to a specific commit and discards all changes in the working directory and staging area.

**Scenario:**
- You want to completely undo a commit and discard all changes.

**Example Steps:**

1. **Current Commit History:**
   ```
   * f666091 (HEAD -> master) WIP
   * 111bd75 Update terms of service and Google Map SDK version.
   ```

2. **Execute Hard Reset:**
   ```sh
   git reset --hard HEAD
   ```

3. **Result:**
   - The commit `088455d` is undone.
   - All changes in `terms.txt` are discarded.
   - HEAD points to `f666091`.

4. **Verify Changes:**
   ```sh
   git status -s
   ```
   No changes should be shown, as everything is reset to `f666091`.

### Summary

- **Soft Reset:** Keeps changes staged.
- **Mixed Reset:** Keeps changes in the working directory but unstaged.
- **Hard Reset:** Discards all changes and resets to a specific commit.

These reset modes help manage your commit history and working state, allowing you to correct mistakes or refine your project’s history as needed.