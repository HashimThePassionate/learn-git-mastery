
1. **Create a new branch and switch to it:**
   ```sh
   git switch -C feature/change-password
   ```

2. **Make your changes** (edit files, add new files, etc.).

3. **Stage the changes:**
   ```sh
   git add .
   ```

4. **Commit the changes:**
   ```sh
   git commit -m "Made changes related to change-password feature"
   ```

5. **Add the new branch to the remote repository (origin):**
   ```sh
   git push origin feature/change-password
   ```

6. **Switch back to the main branch (or any other branch you want to switch to):**
   ```sh
   git switch main
   ```

7. **Delete the local branch:**
   ```sh
   git branch -d feature/change-password
   ```

8. **Delete the remote branch:**
   ```sh
   git push origin --delete feature/change-password
   ```

Here is the sequence of commands you will use:

```sh
# Step 1
git switch -C feature/change-password

# Step 2
# (Make changes to files in your repository)

# Step 3
git add .

# Step 4
git commit -m "Made changes related to change-password feature"

# Step 5
git push origin feature/change-password

# Step 6
git switch main

# Step 7
git branch -d feature/change-password

# Step 8
git push origin --delete feature/change-password
```
