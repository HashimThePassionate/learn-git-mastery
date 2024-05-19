Certainly! Here's a step-by-step guide to fork a repository, keep it up to date with the original repository (upstream), and add the original repository as the base URL:

### Steps to Fork a Repository and Keep it Up to Date:

#### 1. Fork the Repository:
   - Go to the GitHub page of the repository you want to fork.
   - Click on the "Fork" button in the top-right corner of the page.
   - Select your GitHub username or organization where you want to fork the repository.

#### 2. Clone the Forked Repository:
   - Copy the URL of your forked repository from the address bar.
   - Open your terminal or command prompt.
   - Navigate to the directory where you want to clone the repository.
   - Run the following command to clone the forked repository to your local machine:
     ```sh
     git clone https://github.com/hashimthepassionate/mars.git MarsProject
     cd MarsProject
     ```

#### 3. Add the Upstream Remote:
   - Copy the URL of the original repository (the one you forked from).
   - In the terminal, navigate to your forked repository directory.
   - Run the following command to add the original repository as the upstream remote:
     ```sh
     git remote add upstream https://github.com/hashimthepassionate/moon.git
     ```

#### 4. Verify Remote Setup:
   - To verify that the remotes have been set up correctly, run:
     ```sh
     git remote -v
     ```
   - You should see both `origin` (your fork) and `upstream` (original repository) listed.

#### 5. Keep Fork Up to Date:
   - Regularly fetch changes from the original repository to keep your fork up to date.
   - In your terminal, while inside the forked repository directory, run:
     ```sh
     git fetch upstream
     git merge upstream/main
     ```
     This fetches changes from the original repository's main branch (assuming the original repository's default branch is named `main`) and merges them into your forked repository's main branch.

#### 6. Push Changes to Your Fork (Optional):
   - If you've made changes to your fork and want to push them to your GitHub repository, use:
     ```sh
     git push origin main
     ```

#### Summary:
By forking a repository, adding the original repository as the upstream remote, and regularly fetching changes from the upstream repository, you can keep your fork up to date with the latest changes. This ensures that your fork remains synchronized with the original repository and allows you to contribute to the project effectively.