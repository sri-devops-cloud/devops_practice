# Git Reflog: Recover a Deleted Branch

## Objective
To learn how to recover a deleted Git branch using `git reflog`.

## Commands and Procedure

1. Create and switch to a practice branch:
   ```bash
   git switch -c feature/reflog-demo
   ```

2. Create a file and commit it:
   ```bash
   echo "Practice Git reflog recovery" > reflog_demo.txt
   git add reflog_demo.txt
   git commit -m "Add reflog recovery demo"
   ```

3. Switch to main and delete the practice branch:
   ```bash
   git switch main
   git branch -D feature/reflog-demo
   ```

4. Find the previous commit:
   ```bash
   git reflog --oneline
   ```

5. Recover the deleted branch using the actual commit hash:
   ```bash
   git branch feature/reflog-demo <commit-hash>
   ```

6. Verify the recovered branch:
   ```bash
   git branch
   git switch feature/reflog-demo
   git log -1 --oneline
   ```

## Conclusion
Git reflog records recent changes to HEAD and branch references. It can help recover a deleted branch when the relevant commit is still available.
