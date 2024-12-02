# 🛠️ Configuring Git on Windows

This guide will help you configure Git with essential settings for Windows. Configuration can be done at three levels: **System**, **Global**, and **Local**. Let's dive in! 🚀

## 📑 Table of Contents

1. [**Git Configuration Levels**](#-git-configuration-levels) 🔧
2. [**Settings for the Global Level**](#-settings-for-the-global-level) 🌐
   - [1. Set Your Username](#-1-set-your-username) 👤
   - [2. Set Your Email](#-2-set-your-email) 📧
   - [3. Set Your Default Editor](#-3-set-your-default-editor) 📝
   - [4. View Your Global Configuration](#-4-view-your-global-configuration) 👀
   - [5. Configure Line Endings](#-5-configure-line-endings) 🔄
   - [6. Additional Line Ending Configuration (Optional)](#-6-additional-line-ending-configuration) ⚙️
3. [**Common Mistake to Avoid**](#-common-mistake-to-avoid) ❌


## 🔧 Git Configuration Levels

Git configurations can be applied at three different levels, each with its own scope:

- **System** 🖥️: Applies to all users on the system and all repositories.
- **Global** 🌐: Applies to all repositories for the current user.
- **Local** 📂: Applies only to the current repository.

Understanding these levels helps in managing settings effectively across different projects and environments.


## 🌐 Settings for the Global Level

Configuring Git at the global level sets preferences that apply to all repositories for the current user. Here are the essential settings you should configure:

### 👤 1. Set Your Username

To set your username for all repositories of the current user:

```sh
git config --global user.name "Muhammad Hashim"
```

*Note: Use double quotes because the name contains spaces.*

### 📧 2. Set Your Email

To set your email address for all repositories of the current user:

```sh
git config --global user.email hashiimtahir@gmail.com
```

*Note: Double quotes are not necessary here as there are no spaces.*

### 📝 3. Set Your Default Editor

To set Visual Studio Code as your default editor:

```sh
git config --global core.editor "code --wait"
```

*Note: The `--wait` option tells Git to wait until you close the editor before it continues processing.*

### 👀 4. View Your Global Configuration

To view and edit the global configuration settings in Visual Studio Code:

```sh
git config --global -e
```

*This command opens the global Git configuration file in VS Code.*

### 🔄 5. Configure Line Endings

To avoid conflicts between different operating systems by normalizing line endings:

```sh
git config --global core.autocrlf true
```

*Explanation: This setting converts line endings to `CRLF (\r\n)` on checkout and back to `LF (\n)` on commit. This helps in maintaining consistent line endings across different environments, particularly when working with Windows.*

### ⚙️ 6. Additional Line Ending Configuration

If you are working across multiple platforms, you might consider using:

```bash
git config --global core.autocrlf input
```

*Explanation: This setting converts `CRLF` to `LF` on commit but leaves files with `LF` in your working directory, which is typically the format used on Unix-based systems.*


## ❌ Common Mistake to Avoid

- **Do not set `core.autocrlf` to `false` on Windows** unless you are certain that your team consistently uses `LF` line endings across all platforms. Setting it to `false` can cause inconsistencies in line endings, leading to potential issues when collaborating with developers on different operating systems.

Regards,
**Muhammad Hashim** 👨‍💻
