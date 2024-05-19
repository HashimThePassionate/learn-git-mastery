The golden rule of rewriting history in Git is: **Never rewrite history that has been pushed to a shared repository.**

### Explanation

1. **Impact on Collaboration**: When you rewrite history on a shared branch, it changes the commit IDs of the modified commits. This can create significant issues for collaborators who have already based their work on the previous commit history. Their local copies will diverge from the remote repository, leading to complex and confusing merge conflicts.

2. **Commit IDs Change**: Each commit in Git is identified by a unique hash. When you rewrite history, even if the changes seem minor (like editing commit messages or squashing commits), the commit hashes will change. This makes it impossible for Git to automatically reconcile the new history with the old history.

3. **Force Pushing**: Rewriting history typically requires a force push (`git push --force`), which forcibly updates the remote branch to match your local branch. This can overwrite others' work if they have pushed changes after your last pull, leading to data loss or the need to manually resolve conflicts.

### Best Practices

- **Rewrite Locally Before Sharing**: If you need to rewrite history, do so on local branches that have not yet been pushed to the shared repository. This ensures that no one else is affected by the changes.

- **Communicate with Your Team**: If you absolutely must rewrite shared history (which should be rare and only for critical issues like removing sensitive data), communicate clearly with your team. Make sure everyone knows to backup their work and understand the steps they need to take after the rewrite.

- **Use Feature Branches**: Develop features and fixes in separate branches. Only rewrite history in these feature branches before they are merged into the main branch. Once merged, consider the history immutable.

- **Backup the Repository**: Before rewriting history, always create a backup of the repository to safeguard against accidental data loss.

### Summary

Adhering to the golden rule of not rewriting shared history helps maintain a stable and reliable collaboration environment. It ensures that the commit history remains consistent for all team members, reducing the risk of conflicts and confusion.