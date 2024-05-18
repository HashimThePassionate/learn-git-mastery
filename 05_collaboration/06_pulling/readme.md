## Before Pull:
```bash
git log --oneline --all --graph
* 123abc (HEAD -> main, origin/main) Initial commit
* 456def (origin/main) Updated README file
```

1. **Perform Pull Operation:**
   - To fetch changes from the remote repository and automatically merge them into the current branch, use:
     ```
     git pull origin main
     ```
   - This command fetches changes from the remote's main branch and merges them into the local main branch.

2. **Check Commit History (Local) After Pull:**
   - After pulling changes, run the command again to see the updated commit history:
     ```
     git log --oneline --all --graph
     ```

   - You'll see a three-way merge commit that incorporates the changes from the remote's main branch into your local main branch. The commit history might look something like this:

     ```bash
     *   789ghi (HEAD -> main) Merge branch 'origin/main' into main
     |\
     | * 456def (origin/main) Updated README file
     * | 123abc (origin/main) Initial commit
     |/  
     * abc123 Your local commit
     ```

3. **Perform Rebase Merge:**
   - To perform a rebase merge, you can use interactive rebase or a regular rebase. Here, let's use interactive rebase:
     ```
     git rebase -i HEAD~2
     ```
   - This command will open an editor where you can choose how to rebase your commits.

4. **Squash Commits (Optional):**
   - In the interactive rebase editor, you can squash commits or reorder them as needed.
   - Save and exit the editor.

5. **Check Commit History (Local) After Rebase Merge:**
   - After rebasing, run the same command again to see the updated commit history:
     ```
     git log --oneline --all --graph
     ```

   - You'll see a linear commit history after the rebase merge, with the changes from the remote's main branch incorporated into your local main branch.
