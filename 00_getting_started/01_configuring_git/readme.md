# Configuring Git

This guide will help you configure Git with essential settings. Configuration can be done at three levels: System, Global, and Local.

### Git Configuration Levels

- **System**: Applies to all users on the system and all repositories.
- **Global**: Applies to all repositories for the current user.
- **Local**: Applies only to the current repository.

### Settings for the Global Level

#### 1. Set Your Username

To set your username for all repositories of the current user:

```sh
git config --global user.name "Muhammad Hashim"
```
*Note: Use double quotes because the name contains spaces.*

#### 2. Set Your Email

To set your email address for all repositories of the current user:

```sh
git config --global user.email hashiimtahir@gmail.com
```
*Note: Double quotes are not necessary here as there are no spaces.*

#### 3. Set Your Default Editor

To set Visual Studio Code as your default editor:

```sh
git config --global core.editor "code --wait"
```
*Note: The `--wait` option tells Git to wait until you close the editor before it continues processing.*

#### 4. View Your Global Configuration

To view and edit the global configuration settings in Visual Studio Code:

```sh
git config --global -e
```
*This command opens the global Git configuration file in VS Code.*

#### 5. Configure Line Endings

To avoid conflicts between different operating systems by normalizing line endings:

```sh
git config --global core.autocrlf true
```
*Explanation: This setting converts line endings to `\r\n` on checkout and back to `\n` on commit. This helps in maintaining consistent line endings across different environments.*

#### 6. Configure Default Branch to Main
```sh
git config --global init.defaultBranch main
```
*Explanation: By default git create defualt branch to master, why we set default barnch to main because github version control hosting default branch is main.*

### Summary

By configuring Git with your username, email, default editor, and line endings, you ensure that your commits are properly attributed, and you have a consistent development environment. 
