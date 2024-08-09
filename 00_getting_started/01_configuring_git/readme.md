# Configuring Git on Windows

This guide will help you configure Git with essential settings for Windows. Configuration can be done at three levels: System, Global, and Local.

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
*Explanation: This setting converts line endings to `CRLF (\r\n)` on checkout and back to `LF (\n)` on commit. This helps in maintaining consistent line endings across different environments, particularly when working with Windows.*

### **Note:**

- **For Windows**: The `core.autocrlf` setting should typically be set to `true`. This is recommended to avoid issues when sharing code with developers on Unix-based systems (e.g., Linux, macOS).
- **For macOS/Linux**: If you are configuring Git on a Unix-based system, the equivalent setting would be `input` to convert `CRLF` to `LF` on commit but leave files as `LF` in the working directory.

#### 6. Additional Line Ending Configuration (Optional)

If you are working across multiple platforms, you might consider using:

```bash
git config --global core.autocrlf input
```

*Explanation: This setting converts CRLF to LF on commit but leaves files with LF in your working directory, which is typically the format used on Unix-based systems.*

### Common Mistake to Avoid

- **Do not use `core.autocrlf` set to `false` on Windows** unless you are sure that your team is consistently using LF line endings across all platforms. This could cause inconsistencies in line endings across different environments.
