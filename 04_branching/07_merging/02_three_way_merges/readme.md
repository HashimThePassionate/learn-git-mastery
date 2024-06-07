### Explanation

A three-way merge in Git is a method to merge two branches that have diverged. Unlike a fast-forward merge, a three-way merge requires Git to create a new merge commit because there are changes in both branches that need to be combined.

The "three-way" refers to the three commits that Git uses to perform the merge:

1. The common ancestor of the two branches (the base).
2. The tip (latest commit) of the current branch (HEAD).
3. The tip (latest commit) of the branch being merged.

### Example Demonstration

Let's create an example from scratch to demonstrate a three-way merge.

#### Step-by-Step Example:

1. **Initialize a Git repository:**

```bash
mkdir git-three-way-merge-demo
cd git-three-way-merge-demo
git init
```

2. **Create a `main` branch and make an initial commit:**

```bash
echo "Initial content" > file.txt
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

4. **Go back to the `main` branch and make another commit:**

```bash
git checkout main
echo "Main branch work" >> file.txt
git add file.txt
git commit -m "Add main branch work"
```

Now, the history looks like this:

```
* Commit 3 (main)
|
| * Commit 2 (feature)
|/
* Initial commit
```

5. **Merge `feature` branch into `main` with a three-way merge:**

```bash
git checkout main
git merge feature
```

Since both branches have diverged (they both have new commits since their common ancestor), Git performs a three-way merge. This process will create a new merge commit. The history will look like this:

```
*   Merge commit (main)
|\
| * Commit 2 (feature)
|/
* Commit 3 (main)
|
* Initial commit
```

### Resulting Merge Commit

The merge commit includes changes from both the `main` and `feature` branches. If there are conflicts, Git will prompt you to resolve them manually.

### Detailed Steps with Commands

Here are all the commands combined to demonstrate the three-way merge:

```bash
# Initialize a Git repository
mkdir git-three-way-merge-demo
cd git-three-way-merge-demo
git init

# Create a main branch and make an initial commit
echo "Initial content" > file.txt
git add file.txt
git commit -m "Initial commit"

# Create a feature branch and make a commit
git checkout -b feature
echo "Feature work" >> file.txt
git add file.txt
git commit -m "Add feature work"

# Go back to the main branch and make another commit
git checkout main
echo "Main branch work" >> file.txt
git add file.txt
git commit -m "Add main branch work"

# Merge feature branch into main with a three-way merge
git checkout main
git merge feature
```

In this example, a three-way merge was necessary because both the `main` and `feature` branches had new commits since their common ancestor. Git used the common ancestor and the latest commits from both branches to create a new merge commit that combines the changes from both branches.