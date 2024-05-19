## Creating Snapshots with VS Code

### Overview
This section outlines the steps to use VS Code's built-in Git integration to create snapshots of your project at different stages.

### Steps

1. **Open Your Project in VS Code**:
    - Launch Visual Studio Code and open the folder containing your project.

2. **Initialize Git Repository (if not already done)**:
    - If your project is not yet under version control, initialize a Git repository by running:
    ```bash
    git init
    ```

3. **Stage Files for Commit**:
    - In the VS Code sidebar, you'll see a Git icon (![Git icon](https://user-images.githubusercontent.com/71040176/136657869-dc7bbd4f-d71d-4b1b-8d64-6f7f6872e0e1.png)). Click on it to open the Source Control view.
    - Review the changes in your project and stage the files you want to include in the snapshot by clicking the "+" icon next to each file or using the "Stage All Changes" button.

4. **Commit Changes**:
    - Once you've staged your changes, enter a commit message in the text box at the top of the Source Control view.
    - Press `Ctrl + Enter` (Windows/Linux) or `Cmd + Enter` (Mac) to commit the changes.

5. **View Commit History**:
    - To view the commit history, click on the clock icon (![Clock icon](https://user-images.githubusercontent.com/71040176/136659982-0f44ec3c-b78e-474d-8347-2ff1d8ebac0d.png)) in the Source Control view.

6. **Create Snapshots at Different Stages**:
    - Repeat steps 3-5 whenever you want to create a snapshot of your project at a different stage.

7. **View Changes Between Snapshots**:
    - To view the differences between snapshots, open the file you want to compare and click on the file's name in the Source Control view. You'll see a comparison view with changes highlighted.

---

By following these steps, you can easily create snapshots of your project at different stages using VS Code's integrated Git features. If you have any questions or need further assistance, feel free to ask!