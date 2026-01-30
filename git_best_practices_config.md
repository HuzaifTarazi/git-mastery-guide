#!/bin/bash
# ==============================================================
# 📘 Git Complete Commands Cheat Sheet (Professional Bash Version)
# ==============================================================
# A premium, professional, fully self-contained Git cheat sheet
# Designed for developers, internal training, or personal reference
# ==============================================================

# -------------------------------------------------------------------
# 📌 1. Git Configuration (First-Time Setup)
# -------------------------------------------------------------------
echo "🛠 Setting up Git configuration..."
git config --global user.name "Your Name"      # ○ Set Git username
git config --global user.email "your@email.com" # ○ Set Git email
git config --global --list                     # ○ List all global configs
git config --global core.editor "code --wait" # ○ Set VS Code as default editor
git config --global init.defaultBranch main   # ○ Set default branch to main

# -------------------------------------------------------------------
# 📌 2. Create or Clone Repository
# -------------------------------------------------------------------
echo "📂 Creating or cloning repositories..."
git init                     # ○ Initialize a new repository
git clone <repo-url>         # ○ Clone an existing repository

# -------------------------------------------------------------------
# 📌 3. Basic Daily Git Commands
# -------------------------------------------------------------------
echo "⚡ Basic daily Git commands..."
git status                   # ○ Check which files are changed
git add <file>               # ○ Stage a single file
git add .                    # ○ Stage all files
git commit -m "Your commit message" # ○ Commit staged changes

# -------------------------------------------------------------------
# 📌 4. Viewing Commit History
# -------------------------------------------------------------------
echo "📜 Viewing commit history..."
git log                      # ○ Full commit history
git log --oneline            # ○ Short, one-line commits
git log --graph --all --decorate # ○ Visual branch graph
git show <commit-id>         # ○ Show details of a specific commit

# -------------------------------------------------------------------
# 📌 5. Branching & Switching
# -------------------------------------------------------------------
echo "🌿 Branching & switching..."
git branch                   # ○ List all branches
git branch <branch-name>     # ○ Create a new branch
git checkout <branch-name>   # ○ Switch to branch
git checkout -b <branch-name> # ○ Create + switch to new branch
git switch <branch-name>     # ○ Alternative switch command
git merge <branch-name>      # ○ Merge branch into current
git branch -d <branch-name>  # ○ Delete branch

# -------------------------------------------------------------------
# 📌 6. Remote Repository Commands
# -------------------------------------------------------------------
echo "🌐 Remote repository commands..."
git remote add origin <repo-url> # ○ Link local to remote
git remote -v                 # ○ List remote URLs
git push origin main          # ○ Push to remote
git push -u origin main       # ○ Push + set upstream
git pull origin main          # ○ Pull changes from remote
git fetch origin              # ○ Fetch changes without merging

# -------------------------------------------------------------------
# 📌 7. Git Stash (Temporary Save Work)
# -------------------------------------------------------------------
echo "💾 Git stash (temporary save)..."
git stash                     # ○ Save unfinished work
git stash list                # ○ List all stashes
git stash apply               # ○ Apply stash without removing
git stash pop                 # ○ Apply stash and remove
git stash drop                # ○ Delete a stash

# -------------------------------------------------------------------
# 📌 8. Undo & Fix Mistakes
# -------------------------------------------------------------------
echo "⚠️ Undo & fix mistakes..."
git restore <file>            # ○ Undo file changes
git restore --staged <file>   # ○ Unstage a staged file
git reset HEAD <file>         # ○ Unstage file from HEAD
git reset --soft <commit-id>  # ○ Undo commit, keep staged
git reset --hard <commit-id>  # ○ Undo commit & discard changes
git revert <commit-id>        # ○ Safe undo → new commit

# -------------------------------------------------------------------
# 📌 9. Rebase (Professional Teams)
# -------------------------------------------------------------------
echo "🔀 Rebase workflow..."
git rebase main               # ○ Rebase onto main
git rebase --abort            # ○ Abort rebase
git rebase --continue         # ○ Continue after conflict

# -------------------------------------------------------------------
# 📌 10. Cherry-Pick (Move Specific Commits)
# -------------------------------------------------------------------
echo "🍒 Cherry-pick specific commits..."
git cherry-pick <commit-id>   # ○ Copy commit from another branch

# -------------------------------------------------------------------
# 📌 11. Tags (Release Versions)
# -------------------------------------------------------------------
echo "🏷 Tags (release versions)..."
git tag                       # ○ List all tags
git tag v1.0.0                # ○ Create new tag
git push origin v1.0.0        # ○ Push tag to remote

# -------------------------------------------------------------------
# 📌 12. Compare Code Changes
# -------------------------------------------------------------------
echo "🔍 Compare changes..."
git diff                       # ○ See unstaged changes
git diff --staged              # ○ See staged changes
git diff <branch1> <branch2>   # ○ Compare branches

# -------------------------------------------------------------------
# 📌 13. Clean & Maintenance
# -------------------------------------------------------------------
echo "🧹 Clean & maintain repository..."
git clean -f                   # ○ Remove untracked files
git clean -fd                  # ○ Remove untracked files & dirs
git gc                         # ○ Optimize repository
git fsck                       # ○ Check repository integrity

# -------------------------------------------------------------------
# 📌 14. Git Aliases (Productivity)
# -------------------------------------------------------------------
echo "🚀 Productivity aliases..."
git config --global alias.st status   # ○ Shortcut: git st → git status
git config --global alias.cm "commit -m" # ○ Shortcut: git cm → commit
git config --global alias.br branch   # ○ Shortcut: git br → branch

# -------------------------------------------------------------------
# 📌 15. Most Used Git Commands in Companies
# -------------------------------------------------------------------
echo "🏢 Most used commands in corporate workflow..."
git status
git add .
git commit -m "message"
git push
git pull
git fetch
git branch
git checkout
git switch
git merge
git rebase
git stash
git log --oneline
git diff
git reset
git revert

# -------------------------------------------------------------------
# 📌 16. Real Corporate Workflow Example
# -------------------------------------------------------------------
echo "💼 Real workflow example..."
git checkout -b feature/login
git add .
git commit -m "Add login feature"
git push origin feature/login
git checkout main
git pull
git merge feature/login

# -------------------------------------------------------------------
# 📌 17. Git Best Practices
# -------------------------------------------------------------------
echo "✅ Git best practices:"
# ○ Never push directly to main branch
# ○ Always use feature branches
# ○ Write meaningful commit messages
# ○ Pull before pushing
# ○ Use Pull Requests (PRs)
# ○ Rebase or squash commits before merging
# ○ Keep commits small and clean

# ==============================================================
# End of Git Cheat Sheet
# ==============================================================
