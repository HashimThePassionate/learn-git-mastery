
# ✍️ Committing Changes in Git
## 📑 Table of Contents

1. [**1. Commit with a Message Inline**](#-1-commit-with-a-message-inline) 📝
2. [**2. Commit with a Detailed Message**](#-2-commit-with-a-detailed-message) 🗒️
3. [**Summary**](#-summary) 📝


## 📝 1. Commit with a Message Inline

You can commit changes and add a commit message inline using the `-m` flag with the `git commit` command. This is a quick way to record changes with a concise message. 🚀

### 📌 Syntax

```bash
git commit -m "Your commit message here"
```

### 🛠️ Example

```bash
git commit -m "Initial Commit"
```

### 📝 Explanation

- **`git commit`**: Records the staged changes in the repository.
- **`-m "Initial Commit"`**: Adds a commit message inline. The message should briefly describe the changes made.

*Best Practice:* Keep your commit messages clear and descriptive to make it easier to understand the history of your project.


## 🗒️ 2. Commit with a Detailed Message

If you prefer to provide a detailed commit message along with a description, you can use `git commit` without the `-m` flag. This method opens a default text editor (usually Vim or Nano) where you can write a more comprehensive message. 🖋️

### 📌 Syntax

```bash
git commit
```

### 🛠️ Example

```bash
git commit
```

### 📝 Steps

1. **Run the Commit Command**: Executing `git commit` without the `-m` flag will open your default text editor.

2. **Write Your Commit Message**:
    - **Subject Line**: Start with a brief summary of the changes (50 characters or less).
    - **Blank Line**: Leave a blank line after the subject.
    - **Detailed Description**: Provide a more detailed explanation of the changes, including the why and how.

    ```
    Add user authentication feature

    Implemented user login and registration functionality.
    Added JWT token-based authentication.
    Updated the user model and authentication routes.
    ```

3. **Save and Close the Editor**:
    - **Vim**:
        - Press `i` to enter insert mode.
        - Type your message.
        - Press `Esc`, then type `:wq` and hit `Enter` to save and quit.
    - **Nano**:
        - Type your message.
        - Press `Ctrl + O` to save, then `Ctrl + X` to exit.

### 📝 Explanation

- **Detailed Commit Messages**: Providing a detailed message helps in understanding the context and reasoning behind changes, which is invaluable for future reference and collaboration.

*Tip:* Use the imperative mood in your commit messages (e.g., "Add feature" instead of "Added feature") to maintain consistency.


## 📝 Summary

- **Commit with a Brief Message Inline**:
    - Use `git commit -m "message"` to quickly commit changes with a concise message.
    - Ideal for small, straightforward changes.

- **Commit with a Detailed Message**:
    - Use `git commit` to open an editor and add a comprehensive commit message.
    - Best for complex changes that require more explanation.


🎉 **Great Job!** 🎉 You've successfully learned how to commit changes in your Git repository with both brief and detailed messages. Committing thoughtfully is essential for maintaining a clear and understandable project history. 🚀


**Regards,**
**Muhammad Hashim** 👨‍💻
