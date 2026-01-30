# 📘 Git Commands Cheat Sheet (From Setup to Advanced)
---

# 📌 1. Git Configuration (First-Time Setup)

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
git config --global --list
git config --global core.editor "code --wait"
git config --global init.defaultBranch main

```
Explanation: <br>

○ Sets your Git username and email <br>
○ Sets default branch name to main <br>
○ Configures VS Code as default editor <br>

# 📌 2. Create or Download Repository

```bash

git init
git clone <repo-url>

```
Explanation: <br>
○ git init → Create a new Git repository <br>
○ git clone → Download an existing repository <br>

# 📌 3. Basic Daily Git Commands

```bash

git status
git add <file>
git add .
git commit -m "Your commit message"

```
Explanation: <br>
○ git status → Check file changes <br>
○ git add → Stage files for commit <br>
○ git commit → Save changes permanently in Git history <br>

# 📌 4. Viewing Commit History

```bash

git log
git log --oneline
git log --graph --all --decorate
git show <commit-id>

```
Explanation: <br>
○ git log → View full commit history <br>
○ git log --oneline → Short, one-line commits <br>
○ git log --graph --all --decorate → Visualize branches and commits <br>
○ git show <commit-id> → Show details of a specific commit <br>

# 📌 5. Branching

```bash

git branch
git branch <branch-name>
git checkout <branch-name>
git checkout -b <branch-name>
git switch <branch-name>
git merge <branch-name>
git branch -d <branch-name>

```
Explanation: <br>
○ Branch = separate workspace for features <br>
○ git checkout -b → Create and switch to a new branch <br>
○ git merge → Combine feature branch into main <br>
○ git branch -d → Delete a branch <br>

# 📌 6. Remote Repository Commands

```bash

git remote add origin <repo-url>
git remote -v
git push origin main
git push -u origin main
git pull origin main
git fetch origin

```
Explanation: <br>
○ git remote add → Link your local repo to a remote repo <br>
○ git push → Upload changes to remote <br>
○ git pull → Download and merge remote changes <br>
○ git fetch → Download remote changes without merging <br>

# 📌 7. Git Stash (Temporary Save Work)

```bash

git stash
git stash list
git stash apply
git stash pop
git stash drop


```
Explanation: <br>
○ Temporarily save unfinished work <br>
○ Useful when switching branches quickly <br>
○ git stash pop → Apply changes and remove from stash <br>

#  📌 8. Undo & Fix Mistakes

```bash

git restore <file>
git restore --staged <file>
git reset HEAD <file>
git reset --soft <commit-id>
git reset --hard <commit-id>
git revert <commit-id>

```
Explanation: <br>
○ git restore → Undo changes in a file <br>
○ git reset --soft → Undo commit but keep changes staged <br>
○ git reset --hard → Delete commit and all changes (use carefully) <br>
○ git revert → Safe undo that creates a new commit <br>

#  📌 9. Rebase (Professional Teams)

```bash

git rebase main
git rebase --abort
git rebase --continue


```
Explanation: <br>
○ Rewrite history to keep commits clean <br>
○ git rebase --abort → Cancel rebase <br>
○ git rebase --continue → Continue after resolving conflicts <br>

#  📌 10. Cherry-Pick (Move Specific Commits)

```bash

git cherry-pick <commit-id>

```
Explanation: <br>
○ Copy a specific commit from one branch to another <br>
○ Useful for hotfixes <br>

#  📌 11. Tags (Release Versions)

```bash

git tag
git tag v1.0.0
git push origin v1.0.0

```
Explanation: <br>
○ Tags mark specific releases <br>
○ Useful for version control in production <br>

#  📌 12. Compare Code Changes

```bash

git diff
git diff --staged
git diff <branch1> <branch2>


```
Explanation: <br>
○ git diff → See unstaged changes <br>
○ git diff --staged → See staged changes <br>
○ Compare differences between branches <br>
