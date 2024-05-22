# What is Merging
Merging in Git combines changes from different branches into a single branch, integrating divergent development efforts. It reconciles conflicting modifications and creates a unified history of changes, facilitating collaboration and code integration in software development projects.

## Two Types of Merge

1. **Fast Forward Merge**
2. **3-Way Merge**

### Fast Forward Merge:

- Occurs when the branch being merged has all commits accessible from the branch you're merging into.
- Git simply moves the pointer of the branch you're merging into forward to the same commit as the branch you're merging.
- It's fast because it doesn't involve creating a new merge commit.
- Typically happens in linear histories.

### 3-Way Merge:

- Happens when there are divergent changes in both branches being merged.
- Git finds the common ancestor commit of both branches and compares the changes made in each branch since that common ancestor.
- It then combines these changes into a new merge commit, integrating the changes from both branches.
- This type of merge is necessary to reconcile conflicting changes and create a new unified state.