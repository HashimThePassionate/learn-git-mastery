# Rebasing

1. **Switch to a New Branch:**
   - Command: `git switch -C feature/shpping-cart`
   - Output: `Switched to a new branch 'feature/shpping-cart'`

2. **Add a File and Commit Changes:**
   - Commands:
     ```
     echo Hello > cart.txt
     git add .
     git commit -m "Add cart.txt"
     ```
   - Output: None

3. **Display Commit History:**
   - Command: `git log --oneline --all --graph`
   - Output:
     ```
     * 57430d3 (HEAD -> feature/shpping-cart) Add cart.txt
     * 2ced86d (master) Squash Merge
     * 56ea239 Revert "Merge branch 'bugfix'"
     *   ad4f937 Merge branch 'bugfix'
     |\
     | * d0e95c0 Commit passwords
     | * 49a023f Bugfix branch
     * | 4404bdd audience
     * | d7d7464 master
     * | 84d855e master branch
     |/
     * a642e12 Add header to all pages.
     * 50db987 Include the first section in TOC.
     ...
     ```

4. **Switch to Master Branch:**
   - Command: `git switch master`
   - Output: `Switched to branch 'master'`

5. **Update a File and Commit Changes:**
   - Commands:
     ```
     echo Hello >> toc.txt
     git commit -am "update toc"
     ```
   - Output: None

6. **Rebase the Feature Branch onto Master:**
   - Commands:
     ```
     git switch feature/shpping-cart
     git rebase master
     ```
   - Output: `Successfully rebased and updated refs/heads/feature/shpping-cart.`

7. **Display Updated Commit History:**
   - Command: `git log --oneline --all --graph`
   - Output:
     ```
     * 9340bfd (HEAD -> feature/shpping-cart) Add cart.txt
     * 16b1403 (master) update toc
     * 2ced86d Squash Merge
     * 56ea239 Revert "Merge branch 'bugfix'"
     *   ad4f937 Merge branch 'bugfix'
     |\
     | * d0e95c0 Commit passwords
     | * 49a023f Bugfix branch
     * | 4404bdd audience
     * | d7d7464 master
     * | 84d855e master branch
     |/
     * a642e12 Add header to all pages.
     * 50db987 Include the first section in TOC.
     ...
     ```

8. **Merge the Feature Branch into Master:**
   - Commands:
     ```
     git switch master
     git merge feature/shpping-cart
     ```
   - Output: Fast-forward merge message and file changes if applicable.

9. **Check for Conflicts:**
   - Command: `git status -s`
   - Output: `?? toc.txt.orig`

10. **Resolve Merge Conflict:**
    - Commands:
      ```
      git mergetool
      git rebase --continue
      ```
    - Output: Commands to resolve merge conflicts and continue with the rebase process.

11. **Cleanup Backup Files:**
    - Commands:
      ```
      rm toc.txt.orig
      git config --global mergetool.keepBackup false

The command `git config --global mergetool.keepBackup false` modifies a Git configuration setting globally. Here's what each part of the command does:

- `git config`: This command is used to get and set configuration variables that control various aspects of Git's operation.
- `--global`: This flag specifies that the configuration change should be applied globally, affecting all repositories on the system for the current user. Without this flag, the configuration would only apply to the current repository.
- `mergetool.keepBackup`: This is the specific configuration variable being modified. It controls whether Git should keep backup files when using a merge tool to resolve conflicts during a merge or rebase operation.
- `false`: This sets the value of `mergetool.keepBackup` to `false`, indicating that Git should not keep backup files. When this setting is enabled (set to `true`), Git creates backup copies of conflicting files during a merge or rebase operation with a `.orig` extension.

Explanation:
During a merge or rebase operation, Git might encounter conflicts when attempting to automatically resolve changes from different branches. When a conflict occurs, Git provides options to manually resolve the conflict using a merge tool.

By default, when you use a merge tool to resolve conflicts, Git creates backup copies of the conflicting files with a `.orig` extension. These backup files serve as a safety measure in case something goes wrong during the conflict resolution process.

However, in some cases, users may prefer not to clutter their working directory with backup files, especially if they are confident in their ability to resolve conflicts correctly and do not need the safety net provided by backup files. In such cases, setting `mergetool.keepBackup` to `false` instructs Git to skip creating backup files during conflict resolution.

In summary, `git config --global mergetool.keepBackup false` configures Git to not keep backup files during conflict resolution, providing a cleaner working directory without clutter from backup copies.