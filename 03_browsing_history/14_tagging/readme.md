## Tagging Commits

### Introduction
Git tagging allows you to assign meaningful names to specific commits, marking them as important milestones or versions in your project's history. This section demonstrates how to create and manage tags in Git.

### Creating Tags

#### 1. Create Lightweight Tag
```bash
git tag v1.3 a642e12
```
- Creates a lightweight tag named `v1.3` pointing to the specified commit (`a642e12`).

#### 2. Create Annotated Tag
```bash
git tag -a v1.0 -m "Initial Tag for commit" ca49180
```
- Creates an annotated tag named `v1.0` with a message ("Initial Tag for commit") and points it to the specified commit (`ca49180`).

### Viewing and Managing Tags

#### 3. View Tags
```bash
git tag
```
- Displays a list of all tags in the repository.

#### 4. View Tag Details
```bash
git show v1.0
```
- Shows detailed information about the specified tag (`v1.0`), including the tag message and the commit it points to.

#### 5. Delete Tag
```bash
git tag -d v1.0
```
- Deletes the specified tag (`v1.0`) from the repository.

### Conclusion
Tagging commits in Git allows you to mark significant points in your project's history, such as releases or major milestones. By creating and managing tags, you can organize your repository and easily reference important commits in the future. Experiment with lightweight and annotated tags to suit your project's needs, and use Git's tagging features to enhance your version control workflow.