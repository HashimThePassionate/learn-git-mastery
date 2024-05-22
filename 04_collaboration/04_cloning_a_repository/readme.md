1. **Open Terminal (Linux/Mac) or Git Bash (Windows):**
   - Navigate to the directory where you want to clone the repository.

2. **Clone the Repository: and rename clone repository**
   - Use the `git clone` command followed by the URL of the repository you want to clone. For example:
     ```
     git clone https://github.com/hashimthepassionate/mars.git MarsProject
     ```
3. **Navigate into the New Directory:**
   - Go to MarsProject repository
     ```
     cd MarsProject
     ```
4. **Understanding origin/main and origin/HEAD:**
   - In Git, `origin` refers to the remote repository from which the local repository was cloned.
   - `origin/main` refers to the main branch (`main` can also be `master`, depending on your repository settings) on the remote repository.
   - `origin/HEAD` is a symbolic reference to the currently checked out branch on the remote repository. It typically points to the default branch (`main` or `master`).
   - When you clone a repository, Git sets up a tracking branch called `origin/main` which tracks the remote main branch.

5. **Viewing Remote Repositories:**
   - To view the remote repositories associated with your local repository, use the `git remote -v` command:
     ```
     git remote -v
     ```
   - This command lists the remote URLs along with their associated names (`origin` is the default name).
