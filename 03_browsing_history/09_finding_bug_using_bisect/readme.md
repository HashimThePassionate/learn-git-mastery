## Finding Bugs Using Bisect

### Introduction
Git bisect is a powerful tool for identifying the commit that introduced a bug in your codebase. This section outlines the steps to use `git bisect` effectively.

### Starting Bisect

#### 1. Start Bisect
```bash
git bisect start
```
- Initiates the bisect process, indicating that you're about to start searching for a bug.

### Marking Good and Bad Commits

#### 2. Identify Bad Commit
```bash
git bisect bad
```
- Marks the current HEAD commit as bad, indicating that it contains the bug.

#### 3. Identify Good Commit
```bash
git bisect good ca49180
```
- Marks a known good commit where the bug was not present.
- Replace `ca49180` with the SHA hash of a commit that you know is good.

### Navigating Through Commits

#### 4. Bisect Process
- Git will automatically select a commit between the good and bad commits for you to test.
- Based on your test result, mark the commit as either good or bad using `git bisect good` or `git bisect bad`.

#### 5. Repeat Testing
- Continue testing commits and marking them as good or bad until Git identifies the commit that introduced the bug.

### Resetting Bisect

#### 6. Reset Bisect
```bash
git bisect reset
```
- Ends the bisect process and returns the repository to its original state.

### Conclusion
Git bisect is a valuable tool for efficiently pinpointing the source of bugs in your codebase by systematically narrowing down the range of commits where the bug was introduced. By marking known good and bad commits, Git can automatically guide you to the commit that introduced the bug, saving time and effort in debugging.