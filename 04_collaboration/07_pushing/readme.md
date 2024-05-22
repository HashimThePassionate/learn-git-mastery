## Before Changes:
```bash
git log --oneline --all --graph
* 123abc (HEAD -> main) Initial commit
* 456def Updated README file
```
1. **Local Changes:**
   - Make changes to a file (e.g., README) in your local repository.

   ```bash
   git log --oneline --all --graph
   * 123abc (HEAD -> main) Initial commit
   * 456def Updated README file
   * 789ghi Your local changes
   ```

2. **Push Local Changes:**
   - Push your local changes to the remote repository:
     ```
     git push origin main
     ```

3. **Remote Changes:**
   - Someone else adds new changes to the remote repository.

   ```bash
   git log --oneline --all --graph
   * 123abc (HEAD -> main, origin/main) Initial commit
   * 456def Updated README file
   * 012xyz New changes from remote
   ```

4. **Pull and Rebase:**
   - Pull the changes from the remote repository and rebase your local changes on top:
     ```
     git pull --rebase origin main
     ```

   - Resolve any conflicts if necessary.

5. **Check Commit History After Pull and Rebase:**

   ```bash
   git log --oneline --all --graph
   * 123abc (origin/main) Initial commit
   * 456def Updated README file
   * 012xyz New changes from remote
   * 789ghi (HEAD -> main) Your local changes
   ```

6. **Push Rebased Changes:**
   - Push the rebased changes to the remote repository:
     ```
     git push origin main
     ```

7. **Final Commit History After Push:**

   ```bash
   git log --oneline --all --graph
   * 123abc (origin/main) Initial commit
   * 456def Updated README file
   * 012xyz New changes from remote
   * 789ghi (HEAD -> main) Your local changes
   ```
