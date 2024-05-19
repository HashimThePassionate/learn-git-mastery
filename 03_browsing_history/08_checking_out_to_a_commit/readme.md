## Checking Out to a Commit

### Introduction
In Git, you can switch to a specific commit to inspect its state or work from that point using the `git checkout` command. This section demonstrates how to checkout to a specific commit and navigate between commits.

### Checking Out a Commit

#### 1. `git checkout <commit-SHA>`
- Checks out the commit identified by its SHA hash.
- This moves the HEAD pointer to the specified commit, putting the repository in a "detached HEAD" state.

```bash
git checkout b20af3f
```

### Viewing Commits

#### 2. `git log --oneline`
- Displays a concise list of commits in the current branch.
- After checking out a specific commit, some commits may become invisible in the log.

#### 3. `git log --oneline --all`
- Shows all commits in the repository, including those from other branches.
- Useful for viewing the complete commit history even after switching to a specific commit.

### Returning to the Original Branch

#### 4. `git checkout <branch-name>`
- Switches back to the specified branch, moving the HEAD pointer to the latest commit on that branch.

```bash
git checkout main
```

### Conclusion
Using `git checkout`, you can navigate through the commit history of a repository, inspecting the state of the codebase at different points in time. Be cautious when checking out to a specific commit as it puts the repository in a detached HEAD state, where changes made won't be associated with any branch until a new branch is created or an existing one is checked out.