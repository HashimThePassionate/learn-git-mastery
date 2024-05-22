## Filtering Git History

### Introduction
Git provides various options to filter commit history based on different criteria such as the number of commits, author name, date, specific content, and file paths. This section outlines how to use these filters effectively.

### Basic Filters

#### 1. `git log --oneline -3`
- Displays the last 3 commits in a concise one-line format.
  
#### 2. `git log --oneline --author="Muhammad Hashim"`
- Filters commits by author name, showing only commits made by "Muhammad Hashim".

#### 3. `git log --after="2024-04-10"`
- Filters commits by date, showing only commits made after April 10, 2024.

#### 4. `git log --after="yesterday"` or `git log --after="one week ago"`
- Allows specifying relative dates to filter commits, showing commits made after yesterday or one week ago, respectively.

### Content Filters

#### 5. `git log --oneline -S"see"`
- Shows all commits that have the word "see" in their content.

#### 6. `git log --oneline -S"see" --patch`
- Displays the exact changes made in each commit containing the word "see".

### Range Filters

#### 7. `git log --oneline <commit-SHA1>..<commit-SHA2>`
- Shows commits in the range between commit-SHA1 and commit-SHA2, inclusive.

### File Path Filters

#### 8. `git log --oneline <directory>`
- Filters commits by directory name, showing only commits related to files within that directory.

#### 9. `git log --oneline <file-path>`
- Filters commits by a specific file, showing only commits related to changes in that file.

### Conclusion
Understanding how to filter Git history based on various criteria can be immensely helpful in navigating through project development. These filtering options allow you to focus on specific aspects of the commit history, aiding in code review, debugging, and understanding the evolution of the project over time.