#!/bin/bash
# 📘 Git Complete Commands Cheat Sheet (Bash Version)
# Professional Git guide with all commands and explanations inside Bash

# -------------------------------------------------------------------
# 📌 1. Git Configuration (First-Time Setup)

# Set your Git username
git config --global user.name "Your Name"

# Set your Git email
git config --global user.email "your@email.com"

# List all global configurations
git config --global --list

# Set default editor to VS Code
git config --global core.editor "code --wait"

# Set default branch to main
git config --global init.defaultBranch main

# Explanation:
# ○ Sets your Git username and email
# ○ Configures VS Code as default editor
# ○ Sets default branch name to main
# ○ Displays all global Git configuration

# -------------------------------------------------------------------
# 📌 2. Create or Clone Repository

# Initialize a new repository
git init

# Clone an existing repository
git clone <repo-url>

# Explanation:
# ○ git init → Create a new Git repository
# ○ git clone → Download an existing repository

# -------------------------------------------------------------------
# 📌 3. Basic Daily Git Commands

# Check current status of files
git status

# Stage a single file
git add <file>

# Stage all files
git add .

# Commit staged changes with a message
git commit -m "Your commit message"

# Explanation:
# ○ git status → Check which files are changed
# ○ git add → Stage files for commit
# ○ git commit → Save staged changes in Git history

# -------------------------------------------------------------------
# 📌 4. Viewing Commit History

# View full commit history
git log

# View short, one-line commit history
git log --oneline

# View commit history graphically with all branches
git log --graph --all --decorate

# Show details of a specific commit
git show <commit-id>

# Explanation:
# ○ git log → View full commit history
# ○ git log --oneline → Short, compact history
# ○ git log --graph --all --decorate → Visualize branch structure
# ○ git show <commit-id> → Details of a specific commit

# -------------------------------------------------------------------
# 📌 5. Branching & Switching

# List all branches
git branch

# Create a new branch
git branch <branch-name>

# Switch to another branch
git checkout <branch-name>

# Create and switch to a new branch
git checkout -b <branch-name>

# Switch to a branch (alternative)
git switch <branch-name>

# Merge another branch into current branch
git merge <branch-name>

# Delete a branch
git branch -d <branch-name>

# Explanation:
# ○ Branch = separate workspace for features
# ○ git checkout -b → Create and switch to new branch
# ○ git merge → Combine feature branch into main
# ○ git branch -d → Delete a branch

# -------------------------------------------------------------------
# 📌 6. Remote Repository Commands

# Link local repository to remote
git remote add origin <repo-url>

# List configured remote repositories
git remote -v

# Push current branch to remote
git push origin main

# Push and set upstream branch
git push -u origin main

# Pull latest changes from remote
git pull origin main

# Fetch remote changes without merging
git fetch origin

# Explanation:
# ○ git remote add → Link local repo to remote
# ○ git push → Upload changes to remote
# ○ git pull → Download and merge changes
# ○ git fetch → Download changes without merging

# -------------------------------------------------------------------
# 📌 7. Git Stash (Temporary Save Work)

# Save unfinished work temporarily
git stash

# List stashed changes
git stash list

# Apply stash without removing it
git stash apply

# Apply stash and remove it
git stash pop

# Delete a stash
git stash drop

# Explanation:
# ○ Temporarily save unfinished work
# ○ Useful when switching branches quickly
# ○ git stash pop → Apply changes and remove from stash

# -------------------------------------------------------------------
# 📌 8. Undo & Fix Mistakes

# Undo changes in a file
git restore <file>

# Unstage a staged file
git restore --staged <file>

# Unstage file from HEAD
git reset HEAD <file>

# Undo last commit but keep changes staged
git reset --soft <commit-id>

# Undo commit and discard all changes (dangerous!)
git reset --hard <commit-id>

# Safe undo: create a new commit to revert changes
git revert <commit-id>

# Explanation:
# ○ git restore → Undo file changes
# ○ git reset --soft → Undo commit but keep staged changes
# ○ git reset --hard → Delete commit and changes (careful!)
# ○ git revert → Safe undo creating a new commit

# -------------------------------------------------------------------
# 📌 9. Rebase (Professional Teams)

# Rebase current branch onto main
git rebase main

# Abort rebase
git rebase --abort

# Continue after resolving conflicts
git rebase --continue

# Explanation:
# ○ Rewrite commit history to keep it clean
# ○ git rebase --abort → Cancel rebase
# ○ git rebase --continue → Continue after resolving conflicts

# -------------------------------------------------------------------
# 📌 10. Cherry-Pick (Move Specific Commits)

# Apply a specific commit to current branch
git cherry-pick <commit-id>

# Explanation:
# ○ Copy a specific commit from another branch
# ○ Useful for hotfixes

# -------------------------------------------------------------------
# 📌 11. Tags (Release Versions)

# List all tags
git tag

# Create a new tag
git tag v1.0.0

# Push tag to remote
git push origin v1.0.0

# Explanation:
# ○ Tags mark specific releases
# ○ Useful for version control in production

# -------------------------------------------------------------------
# 📌 12. Compare Code Changes

# Compare unstaged changes
git diff

# Compare staged changes
git diff --staged

# Compare changes between branches
git diff <branch1> <branch2>

# Explanation:
# ○ git diff → Unstaged changes
# ○ git diff --staged → Staged changes
# ○ Compare differences between branches

# -------------------------------------------------------------------
# 📌 13. Clean & Maintenance

# Remove untracked files
git clean -f

# Remove untracked files and directories
git clean -fd

# Optimize repository
git gc

# Check repository integrity
git fsck

# Explanation:
# ○ git clean → Remove untracked files
# ○ git gc → Optimize repository
# ○ git fsck → Check repository integrity

# -------------------------------------------------------------------
# 📌 14. Git Aliases (Productivity)

# Create alias for status
git config --global alias.st status

# Create alias for commit
git config --global alias.cm "commit -m"

# Create alias for branch
git config --global alias.br branch

# Explanation:
# ○ Shortcuts for faster workflow
# ○ Example: git st → git status

# -------------------------------------------------------------------
# 📌 15. Most Used Git Commands in Companies

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

# Create a feature branch
git checkout -b feature/login

# Stage and commit changes
git add .
git commit -m "Add login feature"

# Push branch to remote
git push origin feature/login

# Merge into main
git checkout main
git pull
git merge feature/login

# Explanation:
# ○ Work on a feature branch
# ○ Commit changes and push to remote
# ○ Merge into main after review

# -------------------------------------------------------------------
# 📌 17. Git Best Practices

# Explanation:
# ○ Never push directly to main branch
# ○ Always use feature branches
# ○ Write meaningful commit messages
# ○ Pull before pushing
# ○ Use Pull Requests (PRs)
# ○ Rebase or squash commits before merging
# ○ Keep commits small and clean

# ✅ End of Git Commands Cheat Sheet
