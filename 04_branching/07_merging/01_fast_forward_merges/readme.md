### Explanation

In Git, merging is a way to integrate changes from different branches. There are two main types of merges: fast-forward merges and no-fast-forward (or true merge) merges.

#### Fast-Forward Merge

A fast-forward merge occurs when the current branch has not diverged from the branch you are merging into it. In this case, Git can simply move the branch pointer forward to the latest commit of the branch being merged. This type of merge does not create a new merge commit.

**Example:**

- You are on branch `main`.
- There is another branch `feature` that was branched off `main`.
- No new commits have been made to `main` since `feature` branched off.
- When you merge `feature` into `main`, Git simply advances the pointer of `main` to the latest commit of `feature`.

#### No-Fast-Forward Merge

A no-fast-forward merge (also called a true merge) occurs when you explicitly want to keep the history of the branch and create a new merge commit, even if a fast-forward is possible. This is useful to maintain a clear history of when changes were merged.

**Example:**

- You are on branch `main`.
- There is another branch `feature` that was branched off `main`.
- Even if no new commits have been made to `main`, you want to merge `feature` into `main` with a merge commit to signify that a merge occurred.

### Example Demonstration

Let's go through an example to demonstrate both types of merges.

#### Step-by-Step Example:

1. **Initialize a Git repository:**

```bash
mkdir git-merge-demo
cd git-merge-demo
git init
```

2. **Create a `main` branch and make an initial commit:**

```bash
echo "Initial commit" > file.txt
git add file.txt
git commit -m "Initial commit"
```

3. **Create a `feature` branch and make a commit:**

```bash
git checkout -b feature
echo "Feature work" >> file.txt
git add file.txt
git commit -m "Add feature work"
```

4. **Merge `feature` branch into `main` with fast-forward:**

```bash
git checkout main
git merge feature
```

At this point, the history will look like this:

```
*   Commit 2 (feature, main)
|
*   Initial commit
```

Git simply moved the `main` pointer to the latest commit of `feature`.

5. **Create another `feature` branch and make a commit:**

```bash
git checkout -b feature2
echo "Another feature work" >> file.txt
git add file.txt
git commit -m "Add another feature work"
```

6. **Merge `feature2` branch into `main` with no-fast-forward:**

```bash
git checkout main
git merge --no-ff feature2
```

This time, Git will create a new merge commit, resulting in the following history:

```
*   Merge branch 'feature2' into main
|\
| * Commit 3 (feature2)
|/
*   Commit 2 (main)
|
*   Initial commit
```

Here, the merge commit (`Merge branch 'feature2' into main`) indicates that a merge occurred, preserving the history of the `feature2` branch.

### Summary

- **Fast-Forward Merge:** Moves the branch pointer forward to the latest commit of the merged branch without creating a new commit.
- **No-Fast-Forward Merge:** Creates a new merge commit to indicate the merge, preserving the history of both branches.