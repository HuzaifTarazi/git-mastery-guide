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
