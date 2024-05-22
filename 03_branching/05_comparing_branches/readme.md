Let's break down each step:

1. **Switching to the master branch**: 
   ```bash
   git switch master
   ```
   This command switches the current working branch to the master branch.

2. **Checking commits not in master branch**:
   ```bash
   git log --oneline master..bugfix
   ```
   This command lists all the commits that are in the `bugfix` branch but not in the `master` branch. The `--oneline` option shows a concise log output with only the commit messages.

   Output:
   ```
   11deb71 (bugfix) Fixed newly bug
   e2f7a41 Bug fixed
   ```
   This output displays two commits present in the `bugfix` branch that are not in the `master` branch.

3. **Viewing actual changes in bugfix commits**:
   ```bash
   git diff master..bugfix
   ```
   This command shows the differences between the `master` branch and the `bugfix` branch. It displays the changes made in the files between the two branches.

   Output:
   ```
   diff --git a/audience.txt b/audience.txt
   index 4cfef55..c01b824 100644
   --- a/audience.txt
   +++ b/audience.txt
   @@ -1,4 +1,16 @@
    AUDIENCE
   
    This course is for anyone who wants to learn Git.
   -No prior experience is required.
   \ No newline at end of file
   +No prior experience is required.
   +
   +Welcome to venus bugfix branch
   +
   +....................
   +.................
   +.............
   +.........
   +......
   +....
   +..
   +.
   +Another new changes
   \ No newline at end of file
   ```
   This output shows the differences between the `audience.txt` file in the `master` and `bugfix` branches.

4. **Using shorthand to view bugfix changes**:
   ```bash
   git diff bugfix
   ```
   This command is a shorthand for comparing the current branch (master) with the `bugfix` branch. Since we're already on the `master` branch, we omit `master..` in the diff command.

   ```bash
   git diff --name-only bugfix
   ```
   This command shows only the names of the files that are different between the `master` and `bugfix` branches.

   ```bash
   git diff --name-status bugfix
   ```
   This command shows the status of each file that is different between the `master` and `bugfix` branches.

These commands are useful for comparing changes between branches and understanding what changes have been made in different branches.