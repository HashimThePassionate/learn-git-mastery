### Steps:

#### 1. Bob and Alice clone the repository:
Both Bob and Alice clone the repository to their local machines.

```sh
git clone https://github.com/hashimthepassionate/mars.git MarsProject
cd MarsProject
```

#### 2. Bob and Alice create a new branch for their feature:
Each contributor creates a new local branch for their feature.

```sh
git switch -c feature/awesome-feature
```

#### 3. Bob and Alice make changes and commit:
They make changes to the codebase and commit them to their local branches.

```sh
# Make changes
git add .
git commit -m "Implemented awesome feature"
```

#### 4. Bob and Alice pull changes from the main branch:
Before pushing their changes, they fetch and pull the latest changes from the main branch to ensure they're up-to-date.

```sh
git switch main
git pull origin main
```

#### 5. Bob and Alice rebase their feature branches:
To incorporate the latest changes from the main branch into their feature branches, they rebase.

```sh
git switch feature/awesome-feature
git rebase main
```

#### 6. Bob and Alice resolve any conflicts:
If there are any conflicts during the rebase, they resolve them.

#### 7. Bob and Alice push their feature branches:
Once their changes are committed and rebased, they push their feature branches to the remote repository.

```sh
git push origin feature/awesome-feature
```

#### 8. Bob and Alice create pull requests on GitHub:
They go to the repository on GitHub and create pull requests from their feature branches to the main branch.

#### 9. Review and merge pull requests:
Other team members review the pull requests on GitHub, provide feedback, and finally merge them into the main branch.

#### 10. Bob and Alice fetch the latest changes from the main branch:
After the pull requests are merged, they fetch the latest changes from the main branch to their local repositories.

```sh
git switch main
git pull origin main
```

#### 11. Bob and Alice delete their local feature branches:
Once their changes are merged into the main branch, they delete their local feature branches.

```sh
git branch -d feature/awesome-feature
```

#### 12. Bob and Alice delete their remote feature branches:
Optionally, they can delete their remote feature branches.

```sh
git push origin --delete feature/awesome-feature
```

### Summary:
1. Clone the repository.
2. Create a new local branch for the feature.
3. Make changes and commit.
4. Pull changes from the main branch.
5. Rebase the feature branch on the main branch.
6. Resolve conflicts if any.
7. Push the feature branch to the remote.
8. Create pull requests on GitHub.
9. Review and merge pull requests.
10. Fetch latest changes from the main branch.
11. Delete local feature branches.
12. Optionally, delete remote feature branches.
