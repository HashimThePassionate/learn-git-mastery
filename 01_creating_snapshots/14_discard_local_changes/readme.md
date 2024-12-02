# 🗑️ Discard Local Changes in Git 🔄✨

Maintaining a clean working directory is essential for an organized and efficient Git workflow. This guide explains how to **discard local changes** made to tracked files and **remove untracked files** from your Git repository using the `git restore` and `git clean` commands. 🚀🛠️

## 📑 Table of Contents

1. [**1. Discard Local Changes to a Tracked File**](#-1-discard-local-changes-to-a-tracked-file) ✏️🔄
2. [**2. Create a New File and Write Content**](#-2-create-a-new-file-and-write-content) 🆕📄
3. [**3. Check Status for Untracked Files**](#-3-check-status-for-untracked-files) 🔍📊
4. [**4. Remove Untracked Files Completely**](#-4-remove-untracked-files-completely) 🗑️🚫
5. [**Summary**](#-summary) 📝📋

---

## ✏️🔄 1. Discard Local Changes to a Tracked File

Sometimes, you might make changes to a tracked file that you decide not to keep. Git provides a straightforward way to discard these local modifications and revert the file to its last committed state. 🛠️❌

### 📌 Step 1: Make Changes to a File

Start by modifying a tracked file. For example, append the word "fishes" to `moon/main.js`. 🖋️✨

```bash
echo fishes >> moon/main.js
```

*Example:*

```bash
echo fishes >> moon/main.js
```

**What This Does:**
- **`echo fishes >> moon/main.js`**: Appends the word "fishes" to the end of the `main.js` file located in the `moon` directory. If the file doesn't exist, it will be created with the content "fishes".

---

### 📌 Step 2: Add Changes to Staging Area

Add the modified file to the staging area to prepare it for committing. 📂✅

```bash
git add moon/main.js
```

*Example:*

```bash
git add moon/main.js
```

**What This Does:**
- **`git add moon/main.js`**: Stages the changes made to `main.js`, indicating to Git that these changes should be included in the next commit.

---

### 📌 Step 3: Discard Local Changes

If you decide to discard the staged changes and revert the file to its last committed state, use the `git restore --staged` command. 🔄❌

```bash
git restore --staged moon/main.js
```

*Example:*

```bash
git restore --staged moon/main.js
```

**What This Does:**
- **`git restore --staged moon/main.js`**: Removes `main.js` from the staging area, moving the changes back to the unstaged state. The file remains modified in your working directory.

*⚠️ Note:* This command **does not** discard your changes; it merely unstages them. Your modifications remain intact and can be re-staged or discarded as needed.

*💡 Tip:* To completely discard the unstaged changes and revert the file to its last committed state, use:

```bash
git restore moon/main.js
```

*Example:*

```bash
git restore moon/main.js
```

**What This Does:**
- **`git restore moon/main.js`**: Discards all local modifications to `main.js`, restoring it to the state of the last commit.

---

## 🆕📄 2. Create a New File and Write Content

Creating new files is a common task, but sometimes you may decide that a newly created file should not be part of the repository. Here's how to handle such scenarios. 🛠️🗂️

### 📌 Step 1: Create a New File

Create a new file and add content to it. For example, create `file3.js` inside the `moon` directory with the content "Hello". 🆕✨

```bash
echo Hello > moon/file3.js
```

*Example:*

```bash
echo Hello > moon/file3.js
```

**What This Does:**
- **`echo Hello > moon/file3.js`**: Creates a new file named `file3.js` in the `moon` directory with the content "Hello". If the file already exists, it overwrites the existing content.

---

## 🔍📊 3. Check Status for Untracked Files

After creating new files, it's important to check their status to determine whether they are tracked or untracked by Git. 📋🔍

### 📌 Command

```bash
git status -s
```

*Example:*

```bash
git status -s
```

### 📝 Explanation

- **`git status -s`**: Displays the status of your repository in a short format. Untracked files are listed with `??` markers.

**Example Output:**

```
?? moon/file3.js
```

- **`??`**: Indicates that `file3.js` is an untracked file, meaning Git is not currently tracking it.

*💡 Tip:* Regularly checking the status helps in managing which files should be tracked or ignored, maintaining a clean repository.

---

## 🗑️🚫 4. Remove Untracked Files Completely

If you have untracked files that you no longer need, you can remove them from your working directory to keep your repository clean. Git provides the `git clean` command for this purpose. 🛠️❌

### 📌 Step 1: View Help Information for `git clean`

Before removing files, it's wise to understand the available options. Use the `-h` flag to view help information. 📚❓

```bash
git clean -h
```

*Example:*

```bash
git clean -h
```

**What This Does:**
- **`git clean -h`**: Displays help information for the `git clean` command, detailing available options and usage.

### 📌 Step 2: Remove Untracked Files Forcefully

To remove an untracked file, use the `--force` flag with `git clean`. This ensures that Git removes the specified file without prompting for confirmation. 🗑️⚡

```bash
git clean --force moon/file3.js
```

*Example:*

```bash
git clean --force moon/file3.js
```

**What This Does:**
- **`git clean --force moon/file3.js`**: Deletes the untracked file `file3.js` from the `moon` directory permanently.

*⚠️ Warning:* **Use `git clean` with caution**. The `--force` flag will permanently delete files without any confirmation. Ensure that you do not need these files before removing them.

*💡 Tip:* To perform a dry run and see which files would be removed without actually deleting them, use the `-n` flag:

```bash
git clean -n moon/file3.js
```

*Example:*

```bash
git clean -n moon/file3.js
```

**What This Does:**
- **`git clean -n moon/file3.js`**: Shows which files would be removed by `git clean` without actually deleting them. This is useful for verifying which files will be affected.

---

## 📝📋 Summary

- **1. Discard Local Changes to a Tracked File**:
  - **Commands**:
    - `echo fishes >> moon/main.js` ✏️🔄
    - `git add moon/main.js` ➕📂
    - `git restore --staged moon/main.js` 🔄❌
    - *To completely discard changes*: `git restore moon/main.js` ❌✂️
  - **Purpose**: Modify a file, stage changes, and then undo staging or discard changes as needed.

- **2. Create a New File and Write Content**:
  - **Command**: `echo Hello > moon/file3.js` 🆕📄
  - **Purpose**: Create a new file and add content to it.

- **3. Check Status for Untracked Files**:
  - **Command**: `git status -s` 🔍📊
  - **Purpose**: Identify untracked files that are not being tracked by Git.

- **4. Remove Untracked Files Completely**:
  - **Commands**:
    - View help: `git clean -h` 🗑️❓
    - Remove file: `git clean --force moon/file3.js` 🗑️🚫
    - *Dry run*: `git clean -n moon/file3.js` 🛠️🕵️‍♂️
  - **Purpose**: Permanently delete untracked files from the working directory.
