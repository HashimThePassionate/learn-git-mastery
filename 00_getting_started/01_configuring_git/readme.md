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

Setting `git config --global core.autocrlf true` affects how Git handles line endings, particularly in environments where developers are working across different operating systems (e.g., Windows, macOS, Linux). Here’s an overview of the advantages and disadvantages of this setting:

### **Advantages of `core.autocrlf true`**

1. **Cross-Platform Compatibility:**
   - **Automatic Line Ending Conversion:** When you set `core.autocrlf` to `true`, Git automatically converts LF (Line Feed) line endings to CRLF (Carriage Return + Line Feed) when checking out files on Windows. When committing, it converts CRLF back to LF. This ensures that developers using different operating systems can collaborate without worrying about line-ending issues.
   - **Consistency in Repositories:** With this setting, the repository will store all text files with LF endings (the standard in Unix-based systems), while Windows users will see CRLF line endings in their working directory. This consistency prevents issues with scripts or applications that may require specific line endings.

2. **Prevents Unintended Line Ending Changes:**
   - **Avoids "Dirty" Working Directory:** Without this setting, you might see files marked as modified due to line-ending differences even if there were no actual changes. This can be confusing and lead to unnecessary commits. By enabling `core.autocrlf`, Git handles these conversions automatically, preventing such issues.

### **Disadvantages of `core.autocrlf true`**

1. **Unexpected Behavior on Non-Windows Systems:**
   - **Inconsistent Line Endings:** On non-Windows systems, setting `core.autocrlf` to `true` might lead to unintended conversions if files are shared across different environments. For example, if a Linux or macOS developer clones a repository, the line endings will be normalized to LF, but if the same repository is cloned on Windows, the working directory will have CRLF line endings.
   - **Potential Issues with Binary Files:** Although Git tries to avoid converting line endings in binary files, misconfiguration or improper `.gitattributes` settings might lead to corruption of binary files due to line-ending conversions.

2. **Inconvenience for Developers Who Prefer LF:**
   - **Forcing CRLF on Windows:** If you prefer using LF line endings on Windows (for example, to maintain consistency with your team or tooling), `core.autocrlf true` will override your preference, converting line endings to CRLF in your working directory.

### **Preventing the Warning and Ensuring Consistency**

If you want to avoid the warnings about line ending conversions while still using `core.autocrlf true`, here’s what you can do:

1. **Ensure a Proper `.gitattributes` File:**
   - Make sure your repository has a `.gitattributes` file that explicitly defines how line endings should be handled. For example:

     ```bash
     # Handle line endings automatically for files known to be text
     * text=auto

     # Explicitly set text files to use LF endings
     *.sh text eol=lf
     *.json text eol=lf
     *.md text eol=lf

     # Prevent line ending conversion for binary files
     *.png binary
     *.jpg binary
     ```

2. **Avoid Setting `core.autocrlf` Globally:**
   - Instead of setting `core.autocrlf` globally, consider configuring it per repository, especially if you work on projects that require different line-ending settings.

3. **Normalize Line Endings:**
   - Run `git add --renormalize .` in your repository to apply the desired line endings and prevent further warnings.

#### 6. Configure Default Branch to Main
```sh
git config --global init.defaultBranch main
```
*Explanation: By default git create defualt branch to master, why we set default barnch to main because github version control hosting default branch is main.*

### Summary

By configuring Git with your username, email, default editor, and line endings, you ensure that your commits are properly attributed, and you have a consistent development environment. 
