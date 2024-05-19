## Finding the Author of a Line Using Blame

### Introduction
Git provides the `git blame` command to track the origin of each line in a file, showing the commit and author responsible for the changes. This section demonstrates how to use `git blame` to identify the author of specific lines in a file.

### Blaming the File

#### 1. `git blame audience.txt`
- Displays a detailed annotation for each line in the specified file, showing the commit hash, author, timestamp, and content of the last change to each line.

#### 2. `git blame -e -L 1,2 audience.txt`
- Blames only the specified range of lines (in this case, lines 1 to 2) in the file `audience.txt`.
- Includes email addresses of authors in the output.

### Conclusion
Using `git blame`, you can track the history of changes for each line in a file, helping you understand who made which changes and when. This can be valuable for identifying the authors responsible for specific modifications, investigating code changes, and tracing the evolution of a file over time.