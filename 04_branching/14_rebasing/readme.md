Rebasing in Git is a process of moving or applying a sequence of commits from one branch to another. It essentially rewrites the commit history by placing the commits from one branch onto the tip of another branch. This can be useful for maintaining a linear and cleaner commit history, especially when incorporating changes from one branch into another.

### Example Demonstration

Let's go through an example to demonstrate rebasing:

#### Step-by-Step Example:

1. **Initialize a Git repository:**

```bash
mkdir git-rebase-demo
cd git-rebase-demo
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

Now, the history on the `feature` branch looks like this:

```
* Commit 2 (feature)
|
* Commit 1 (main)
|
* Initial commit
```

4. **Go back to the `main` branch and make another commit:**

```bash
git checkout main
echo "Main branch work" >> file.txt
git add file.txt
git commit -m "Add main branch work"
```

Now, the history on the `main` branch looks like this:

```
* Commit 3 (main)
|
* Commit 1 (main)
|
* Initial commit
```

5. **Rebase `feature` branch onto `main` branch:**

```bash
git checkout feature
git rebase main
```

Git will take the commits from the `feature` branch and place them on top of the `main` branch. This creates a linear history where the commits from the `feature` branch are now based on the latest commit of the `main` branch.

### Resulting Rebase

After the rebase, the commit history will look like this:

```
* Commit 2' (feature)
|
* Commit 3 (main)
|
* Commit 1 (main)
|
* Initial commit
```

### Detailed Steps with Commands

Here are all the commands combined to demonstrate rebasing:

```bash
# Initialize a Git repository
mkdir git-rebase-demo
cd git-rebase-demo
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

# Rebase feature branch onto main branch
git checkout feature
git rebase main
```

In this example, the commits from the `feature` branch were rebased onto the `main` branch, resulting in a linear commit history where the changes from the `feature` branch are now based on the latest commit of the `main` branch. Rebasing can help keep the commit history cleaner and easier to follow, especially in collaborative environments.