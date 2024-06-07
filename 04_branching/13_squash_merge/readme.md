A squash merge in Git is a way of merging changes from one branch into another while condensing all the individual commits on the source branch into a single commit on the target branch. This can be useful for keeping the commit history clean and concise, especially when integrating feature branches into a main branch.

### Example Demonstration

Let's go through an example to demonstrate a squash merge:

#### Step-by-Step Example:

1. **Initialize a Git repository:**

```bash
mkdir git-squash-merge-demo
cd git-squash-merge-demo
git init
```

2. **Create a `main` branch and make an initial commit:**

```bash
echo "Initial content" > file.txt
git add file.txt
git commit -m "Initial commit"
```

3. **Create a `feature` branch and make multiple commits:**

```bash
git checkout -b feature
echo "Feature work 1" >> file.txt
git add file.txt
git commit -m "Add feature work 1"

echo "Feature work 2" >> file.txt
git add file.txt
git commit -m "Add feature work 2"
```

Now, the history on the `feature` branch looks like this:

```
* Commit 2 (feature)
|
* Commit 1 (feature)
|
* Initial commit
```

4. **Merge `feature` branch into `main` with squash option:**

```bash
git checkout main
git merge --squash feature
```

Git will apply the changes from the `feature` branch onto the `main` branch, but it will condense all the individual commits from the `feature` branch into a single commit on the `main` branch.

### Resulting Squash Merge Commit

After the squash merge, you will have a new commit on the `main` branch that represents all the changes from the `feature` branch. This commit will contain all the changes introduced by the individual commits on the `feature` branch.

### Detailed Steps with Commands

Here are all the commands combined to demonstrate the squash merge:

```bash
# Initialize a Git repository
mkdir git-squash-merge-demo
cd git-squash-merge-demo
git init

# Create a main branch and make an initial commit
echo "Initial content" > file.txt
git add file.txt
git commit -m "Initial commit"

# Create a feature branch and make multiple commits
git checkout -b feature
echo "Feature work 1" >> file.txt
git add file.txt
git commit -m "Add feature work 1"

echo "Feature work 2" >> file.txt
git add file.txt
git commit -m "Add feature work 2"

# Merge feature branch into main with squash option
git checkout main
git merge --squash feature
```

In this example, the `feature` branch had multiple commits, but after the squash merge, all those commits were condensed into a single commit on the `main` branch. This can help maintain a cleaner commit history, especially for feature branches.