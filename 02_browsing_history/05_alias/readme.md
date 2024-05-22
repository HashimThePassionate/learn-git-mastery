## Creating Git Alias

### Introduction
Git aliases allow you to create shortcuts for frequently used or complex commands, making your Git workflow more efficient. This section demonstrates how to create an alias for the `git log` command with a custom format.

### Creating Alias

#### 1. Define Alias
```bash
git config --global alias.lg "log --pretty=format:'%Cgreen %an%Creset committed %h - %s'"
```
- This command creates a global alias named `lg` for the `git log` command with a custom format.
- The format includes the author's name in green color, followed by the abbreviated commit hash and commit message.

### Usage

#### 2. Using the Alias
```bash
git lg
```
- Executes the `git log` command with the custom format defined by the alias.
- The output displays the author's name in green, followed by the commit hash and message for each commit.

### Conclusion
Creating Git aliases allows you to simplify complex commands or customize their behavior according to your preferences. The `lg` alias created in this example provides a more concise and visually appealing format for viewing commit history. Experiment with aliases to streamline your Git workflow and improve productivity.