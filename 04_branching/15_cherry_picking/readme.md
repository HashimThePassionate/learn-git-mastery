# Cherry picking 
Cherry-picking in Git is the process of selecting specific commits from one branch and applying them to another branch. This allows you to incorporate particular changes without merging entire branches. It's useful for backporting bug fixes or features to different branches without bringing in unrelated changes.

1. **Explanation of Cherry-picking:**
   Cherry-picking in Git is the process of selecting specific commits from one branch and applying them to another branch. It allows you to incorporate particular changes without merging entire branches. This is useful for backporting bug fixes or features to different branches without bringing in unrelated changes.

2. **Git Command:**
   ```git
   git log --oneline --all --graph
   ```
   This command is used to display a concise and graphical representation of the commit history, showing each commit on a single line, along with all branches and their relationships.

3. **Output of git log command:**
   ```
   * 15cdad7 (HEAD -> feature/shpping-cart) add mountains in toc.txt
   * 4e252ae (master) Update toc.txt
   * 9340bfd Add cart.txt
   * 16b1403 update toc
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
   * 555b62e Include the note about committing after staging the changes.
   * 91f7d40 Explain various ways to stage changes.
   * edb3594 First draft of staging changes.
   * 24e86ee Add command line and GUI tools to the objectives.
   * 36cd6db Include the command prompt in code sample.
   * 9b6ebfd Add a header to the page about initializing a repo.
   * fa1b75e Include the warning about removing .git directory.
   * dad47ed Write the first draft of initializing a repo.
   * fb0d184 Define the audience.
   * 1ebb7a7 Define the objectives.
   * ca49180 Initial commit.
   ```

4. **Explanation of git cherry-pick command:**
   ```git
   git switch master
   git cherry-pick 15cdad7
   ```
   These commands switch to the `master` branch and cherry-pick the commit `15cdad7`, which adds "mountains" to the `toc.txt` file, from the `feature/shpping-cart` branch.

5. **Output of git cherry-pick command:**
   ```
   [master 8962751] add mountains in toc.txt
   Date: Sun May 19 01:23:11 2024 +0500
   1 file changed, 1 insertion(+), 1 deletion(-)
   ```

6. **Git Command to display commit history after cherry-picking:**
   ```git
   git log --oneline --all --graph
   ```
   This command is used again to display the commit history after cherry-picking.

7. **Output after cherry-picking:**
   ```
   * 8962751 (HEAD -> master) add mountains in toc.txt        
   | * 15cdad7 (feature/shpping-cart) add mountains in toc.txt
   |/
   * 4e252ae Update toc.txt
   * 9340bfd Add cart.txt
   * 16b1403 update toc
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
   ```

This shows that the commit `15cdad7` from the `feature/shpping-cart` branch has been successfully cherry-picked into the `master` branch.