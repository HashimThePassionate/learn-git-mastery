## Customizing Git Log Output

### Introduction
Git provides flexibility in customizing the format of log output, allowing users to display specific information in a desired format. This section demonstrates various ways to customize the log output according to your preferences.

### Basic Formatting

#### 1. `git log --pretty=format:"Hey %an"`
- Displays a custom message with the author's name.
- **Example Output:** Hey Muhammad Hashim

#### 2. `git log --pretty=format:"%an committed %H"`
- Shows the author's name followed by "committed" and the commit's SHA.
- **Example Output:** Muhammad Hashim committed 06735275dd31d9d3e20a608bcf821fc3a93550c5

#### 3. `git log --pretty=format:"Hey %an %h"`
- Displays a custom message with the author's name and abbreviated commit hash.
- **Example Output:** Hey Muhammad Hashim 0673527

#### 4. `git log --pretty=format:"%an on %cd"`
- Shows the author's name followed by the commit date.
- **Example Output:** Muhammad Hashim on Tue Apr 30 12:47:34 2024 +0500

### Colorized Output

#### 5. `git log --pretty=format:"%Cgreen%an%Creset committed %h on %cd"`
- Formats the author's name in green color followed by "committed", commit hash, and commit date.
- **Example Output:** ![green]Muhammad Hashim![reset] committed 0673527 on Tue Apr 30 12:47:34 2024 +0500

### Conclusion
Customizing the format of Git log output allows for better readability and presentation of commit information. By incorporating specific details and even colorization, you can tailor the log output to suit your preferences or the requirements of your project or team.