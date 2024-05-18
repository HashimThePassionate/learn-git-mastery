### Step 1: Download and Install Git for Windows

1. **Download Git for Windows:**
   - Visit the Git for Windows website: [https://gitforwindows.org](https://gitforwindows.org).
   - Click the "Download" button to get the installer.

2. **Install Git for Windows:**
   - Run the downloaded installer.
   - Follow the installation prompts. Make sure to select the option to use the Git Credential Manager during the installation process. This is usually enabled by default.
   - Complete the installation.

### Step 2: Configure Git to Use the Credential Manager

1. **Open Git Bash:**
   - After installing Git, open Git Bash from the Start menu or your desktop.

2. **Configure Git to Use Credential Manager:**
   - Run the following command in Git Bash to configure Git to use the Windows Credential Manager:
     ```bash
     git config --global credential.helper manager
     ```

### Step 3: Store GitHub Remote Credentials

1. **Clone a Repository or Push Changes to Trigger Credential Prompt:**
   - When you clone a repository or push changes for the first time, Git will prompt you to enter your GitHub credentials.
   - For example, to clone a repository, use:
     ```sh
     git clone https://github.com/hashimthepassionate/mars.git
     ```

2. **Enter GitHub Credentials:**
   - When prompted, enter your GitHub username and password (or personal access token if you have two-factor authentication enabled).
   - The Windows Credential Manager will store these credentials securely.

### Step 4: Verify Stored Credentials

1. **Access Windows Credential Manager:**
   - Open the Control Panel and navigate to "User Accounts" > "Credential Manager".
   - Alternatively, you can search for "Credential Manager" in the Start menu.

2. **Verify GitHub Credentials:**
   - In the Credential Manager, go to the "Windows Credentials" tab.
   - Look for an entry related to `git:https://github.com` or similar.
   - Verify that your GitHub credentials are stored correctly.

### Additional Notes:

- **Updating Credentials:**
  - If you change your GitHub password or personal access token, you can update the stored credentials by deleting the existing entry in the Credential Manager and re-entering your credentials the next time Git prompts you.

- **Security:**
  - Using the Windows Credential Manager helps keep your credentials secure by storing them in an encrypted format.
