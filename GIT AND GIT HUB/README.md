## Getting Started

Here are some essential commands to get you started with Git and GitHub:

### Initialize a local Git repository:

```python
    git init
```

###  Clone a remote repository:

```python
git clone https://github.com/<username>/<repository-name>.git

```

### Check the status of your repository:

```python
   git status

```
### Add files to the staging area:

```python
   git add .  (Adds all new or modified files)
   git add <filename>  (Adds a specific file)

```


### Commit changes with a descriptive message:
```python
   git commit -m "Your commit message"
   git commit -m "Your commit message"
```


### Push changes to a remote repository:
```python
  git push origin <branch-name>
```


## Common Commands

### View a list of branches:
```python
  git branch
```
###  Create a new branch:

```python
  git branch <branch-name>
```


### Switch to a branch:

```python
  git checkout <branch-name>
```

### Merge a branch:

```python
  git merge <branch-name>
```

### Remove a branch:

```python
  git branch -d <branch-name>
```

### View commit history:

```python
  git log

```

### Revert a commit:

```python
  git revert <commit-hash>
```

###  Stash uncommitted changes:

```python
  git stash
```
### Apply stashed changes:

```python
  git stash pop
```

## Additional GitHub-Specific Commands

### Create a pull request:

```python
  gh pr create

```

###  View pull requests:

```python
  gh pr list
```

### Open a pull request in your browser:

```python
  gh pr view
```


### Merge a pull request:

```python
 gh pr merge
```
