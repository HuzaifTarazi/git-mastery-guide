# 📘 Git Complete Commands Cheat Sheet

A comprehensive, professional guide to mastering Git commands for developers of all levels. Perfect for team collaboration and enterprise workflows.

---

## 📌 Table of Contents

1. [Git Configuration](#1-git-configuration)
2. [Create or Clone Repository](#2-create-or-clone-repository)
3. [Basic Daily Git Commands](#3-basic-daily-git-commands)
4. [Viewing Commit History](#4-viewing-commit-history)
5. [Branching & Switching](#5-branching--switching)
6. [Remote Repository Commands](#6-remote-repository-commands)
7. [Git Stash](#7-git-stash)
8. [Undo & Fix Mistakes](#8-undo--fix-mistakes)
9. [Rebase](#9-rebase)
10. [Cherry-Pick](#10-cherry-pick)
11. [Tags & Releases](#11-tags--releases)
12. [Compare Code Changes](#12-compare-code-changes)
13. [Clean & Maintenance](#13-clean--maintenance)
14. [Git Aliases](#14-git-aliases)
15. [Most Used Commands](#15-most-used-git-commands-in-companies)
16. [Corporate Workflow Example](#16-real-corporate-workflow-example)
17. [Best Practices](#17-git-best-practices)

---

## 1. Git Configuration

### First-Time Setup

Configure Git with your personal information before your first commit.

```bash
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
```

### Purpose & Explanation

| Command | Purpose |
|---------|---------|
| `git config --global user.name` | Sets your Git username across all repositories |
| `git config --global user.email` | Sets your Git email for commit identification |
| `git config --global --list` | Displays all global Git configuration settings |
| `git config --global core.editor` | Configures VS Code as your default editor |
| `git config --global init.defaultBranch` | Sets default branch name to main (modern standard) |

---

## 2. Create or Clone Repository

### Initialize or Download a Repository

```bash
# Initialize a new repository in current directory
git init

# Clone an existing repository from remote
git clone <repo-url>
```

### Key Points

| Command | What It Does |
|---------|--------------|
| `git init` | Creates a new local Git repository in your project folder |
| `git clone <repo-url>` | Downloads an entire repository with full history |

---

## 3. Basic Daily Git Commands

### Essential Commands for Daily Development

These four commands form the backbone of everyday Git usage.

```bash
# Check current status of files
git status

# Stage a single file for commit
git add <file>

# Stage all modified files at once
git add .

# Commit staged changes with a message
git commit -m "Your commit message"
```

### Workflow Explanation

| Step | Command | Result |
|------|---------|--------|
| 1 | `git status` | View which files are modified |
| 2 | `git add .` | Stage all changes |
| 3 | `git commit -m "message"` | Save changes to history |

**Pro Tip:** Combine staging and committing with `git commit -am "message"` for tracked files.

---

## 4. Viewing Commit History

### Explore Your Project's History

```bash
# View full commit history with details
git log

# View short, one-line commit history (compact)
git log --oneline

# View commit history graphically with all branches
git log --graph --all --decorate

# Show details of a specific commit
git show <commit-id>
```

### Advanced Viewing Options

| Command | Output |
|---------|--------|
| `git log` | Full commit details including author and date |
| `git log --oneline` | Compact view with commit ID and message |
| `git log --graph --all --decorate` | Visual branch structure and merge points |
| `git show <commit-id>` | Complete details including changes made |

---

## 5. Branching & Switching

### Work on Multiple Features Simultaneously

Branches allow parallel development without affecting the main codebase.

```bash
# List all local branches
git branch

# Create a new branch
git branch <branch-name>

# Switch to another branch (traditional)
git checkout <branch-name>

# Create and switch to a new branch in one command
git checkout -b <branch-name>

# Switch to a branch (modern alternative)
git switch <branch-name>

# Merge another branch into current branch
git merge <branch-name>

# Delete a branch (safe)
git branch -d <branch-name>

# Force delete a branch (use with caution)
git branch -D <branch-name>
```

### Branching Strategy

| Concept | Purpose |
|---------|---------|
| **Main Branch** | Production-ready code |
| **Feature Branch** | Isolated feature development |
| **Hotfix Branch** | Emergency production fixes |
| `git branch` | List available branches |
| `git checkout -b` | Create and switch to new branch |
| `git merge` | Combine feature branch into main |
| `git branch -d` | Delete branch after merging |

---

## 6. Remote Repository Commands

### Connect and Sync with Remote Repositories

```bash
# Link local repository to remote (GitHub, GitLab, etc.)
git remote add origin <repo-url>

# List all configured remote repositories
git remote -v

# Push current branch to remote repository
git push origin main

# Push and set upstream tracking branch
git push -u origin main

# Pull latest changes from remote and merge locally
git pull origin main

# Fetch remote changes without merging locally
git fetch origin

# Remove remote repository link
git remote remove origin
```

### Remote Operations Explained

| Command | Function |
|---------|----------|
| `git remote add origin` | Establish connection to remote repository |
| `git remote -v` | Show all remote repositories with URLs |
| `git push origin` | Upload commits to remote |
| `git push -u origin` | Upload and set upstream branch |
| `git pull origin` | Download and merge remote changes |
| `git fetch origin` | Download changes without merging |

**Key Difference:**
- `git pull` = `git fetch` + `git merge` (automatically merges)
- `git fetch` = only downloads (safe, no auto-merge)

---

## 7. Git Stash

### Temporarily Save Unfinished Work

Perfect for quickly switching contexts without committing incomplete changes.

```bash
# Save unfinished work temporarily
git stash

# List all stashed changes
git stash list

# Apply stash without removing it
git stash apply

# Apply stash and remove it from stash list
git stash pop

# Delete a specific stash
git stash drop

# Delete all stashes
git stash clear
```

### Stash Use Cases

| Scenario | Command |
|----------|---------|
| Need to switch branches quickly | `git stash` |
| Review stashed changes | `git stash list` |
| Apply changes but keep stash | `git stash apply` |
| Apply and remove from stash | `git stash pop` |
| Clean up stashes | `git stash clear` |

---

## 8. Undo & Fix Mistakes

### Safe Ways to Correct Git Mistakes

```bash
# Restore file to last committed state
git restore <file>

# Unstage a file without losing changes
git restore --staged <file>

# Remove file from staging area (older method)
git reset HEAD <file>

# Undo last commit but keep changes staged
git reset --soft HEAD~1

# Undo last commit but keep changes unstaged
git reset --mixed HEAD~1

# Undo commit and discard all changes (DANGEROUS!)
git reset --hard HEAD~1

# Create a new commit that reverts previous commit (SAFE)
git revert <commit-id>

# Amend last commit message
git commit --amend -m "New message"

# Amend last commit with new changes
git commit --amend --no-edit
```

### Undo Methods Compared

| Method | Keeps Changes? | Creates New Commit? | Safety |
|--------|---|---|---|
| `git restore` | Yes | No | ✅ Safe |
| `git reset --soft` | Yes | No | ✅ Safe |
| `git reset --hard` | No | No | ⚠️ Destructive |
| `git revert` | No | Yes | ✅ Safe (Team Friendly) |
| `git commit --amend` | Yes | No | ✅ Safe |

**Pro Tip:** Use `git revert` for team projects (creates transparency), `git reset` only for local branches.

---

## 9. Rebase

### Rewrite History for Clean Commits

Advanced technique used by professional teams to maintain clean commit history.

```bash
# Rebase current branch onto main
git rebase main

# Interactive rebase to squash or reorder commits
git rebase -i HEAD~3

# Abort rebase if conflicts arise
git rebase --abort

# Continue rebase after resolving conflicts
git rebase --continue

# Skip current commit during rebase
git rebase --skip
```

### When to Use Rebase

| Use Case | Command |
|----------|---------|
| Clean up feature branch before merge | `git rebase main` |
| Squash multiple commits | `git rebase -i HEAD~n` |
| Fix merge conflicts | `git rebase --continue` |
| Cancel entire rebase | `git rebase --abort` |

**Important:** Never rebase commits already pushed to shared branches!

---

## 10. Cherry-Pick

### Apply Specific Commits to Another Branch

Useful for hotfixes and applying selective changes.

```bash
# Apply a specific commit to current branch
git cherry-pick <commit-id>

# Cherry-pick multiple commits
git cherry-pick <commit-id1> <commit-id2>

# Continue after resolving conflicts
git cherry-pick --continue

# Abort cherry-pick
git cherry-pick --abort
```

### Real-World Scenarios

| Scenario | Command |
|----------|---------|
| Need hotfix from develop | `git cherry-pick <commit-id>` |
| Apply multiple fixes | `git cherry-pick commit1 commit2` |
| Resolve conflicts during pick | `git cherry-pick --continue` |

---

## 11. Tags & Releases

### Mark Release Versions and Milestones

```bash
# List all tags
git tag

# Create a lightweight tag
git tag v1.0.0

# Create an annotated tag with message
git tag -a v1.0.0 -m "Release version 1.0.0"

# Push single tag to remote
git push origin v1.0.0

# Push all tags to remote
git push origin --tags

# Delete local tag
git tag -d v1.0.0

# Delete remote tag
git push origin --delete v1.0.0
```

### Semantic Versioning

```
v<MAJOR>.<MINOR>.<PATCH>
v1.0.0 = First major release
v1.2.3 = Version 1, minor update 2, patch update 3
```

---

## 12. Compare Code Changes

### View Differences Between Versions

```bash
# Compare unstaged changes in working directory
git diff

# Compare staged changes (in staging area)
git diff --staged

# Compare changes between branches
git diff <branch1> <branch2>

# Compare changes between commits
git diff <commit1> <commit2>

# Compare specific file
git diff <file>

# Show statistics of changes
git diff --stat
```

### Diff Types

| Command | Shows |
|---------|-------|
| `git diff` | Unstaged changes only |
| `git diff --staged` | Staged changes ready to commit |
| `git diff <branch1> <branch2>` | Differences between branches |
| `git diff --stat` | Summary of changes |

---

## 13. Clean & Maintenance

### Optimize and Maintain Repository Health

```bash
# Remove untracked files (preview)
git clean -n

# Remove untracked files (execute)
git clean -f

# Remove untracked files and directories
git clean -fd

# Optimize repository (pack objects)
git gc

# Check repository integrity
git fsck

# Count objects in repository
git count-objects -v
```

### Maintenance Tasks

| Command | Purpose |
|---------|---------|
| `git clean -fd` | Remove all untracked files and folders |
| `git gc` | Optimize repository and reduce size |
| `git fsck` | Detect corruption in repository |

---

## 14. Git Aliases

### Create Shortcuts for Faster Workflow

```bash
# Create alias for status
git config --global alias.st status

# Create alias for commit
git config --global alias.cm "commit -m"

# Create alias for branch
git config --global alias.br branch

# Create alias for log
git config --global alias.lg "log --oneline --graph --all"

# Create alias for checkout
git config --global alias.co checkout

# Create alias for pull with rebase
git config --global alias.pr "pull --rebase"
```

### Popular Aliases

| Alias | Command | Result |
|-------|---------|--------|
| `git st` | `status` | Quick status check |
| `git cm` | `commit -m` | Faster commits |
| `git br` | `branch` | Branch operations |
| `git lg` | `log --oneline --graph --all` | Beautiful history view |
| `git co` | `checkout` | Switch branches quickly |

---

## 15. Most Used Git Commands in Companies

### Daily Essential Commands

These 15 commands cover 95% of professional development needs:

```bash
git status          # Check file status
git add .           # Stage all changes
git commit -m "msg" # Commit changes
git push            # Upload to remote
git pull            # Download from remote
git fetch           # Get updates without merging
git branch          # List branches
git checkout        # Switch branches
git switch          # Modern branch switching
git merge           # Combine branches
git rebase          # Clean commit history
git stash           # Temporarily save work
git log --oneline   # View commit history
git diff            # Compare changes
git reset           # Undo commits
git revert          # Safe undo with new commit
```

---

## 16. Real Corporate Workflow Example

### Complete Feature Development Cycle

**Scenario:** Developing a login feature in a team environment

```bash
# Step 1: Create feature branch from main
git checkout -b feature/login

# Step 2: Make changes and commit
git add .
git commit -m "Add login form component"

# Step 3: Push branch to remote
git push -u origin feature/login

# Step 4: Create Pull Request on GitHub/GitLab
# (Wait for code review and approval)

# Step 5: Return to main branch
git checkout main

# Step 6: Ensure main is up to date
git pull origin main

# Step 7: Merge feature branch
git merge feature/login

# Step 8: Push merged code to remote
git push origin main

# Step 9: Delete feature branch locally
git branch -d feature/login

# Step 10: Delete feature branch on remote
git push origin --delete feature/login
```

### Corporate Branching Strategy

```
main (production)
  ├── hotfix/payment-bug
  └── develop (staging)
       ├── feature/login
       ├── feature/dashboard
       └── feature/auth
```

---

## 17. Git Best Practices

### Professional Development Standards

#### ✅ Do's

- ✅ **Always use feature branches** - Never develop directly on main
- ✅ **Write meaningful commit messages** - Be descriptive and clear
- ✅ **Pull before pushing** - Stay updated with team changes
- ✅ **Use Pull Requests (PRs)** - Enable code review process
- ✅ **Keep commits small** - One feature per commit when possible
- ✅ **Rebase before merging** - Maintain clean history
- ✅ **Review before merging** - Catch bugs early
- ✅ **Tag releases** - Mark production versions clearly

#### ❌ Don'ts

- ❌ **Never force push** - `git push --force` can destroy team work
- ❌ **Don't commit credentials** - Use `.gitignore` for sensitive files
- ❌ **Don't rebase shared branches** - Only rebase local feature branches
- ❌ **Don't use vague messages** - "fixed stuff" is not acceptable
- ❌ **Don't commit large binaries** - Use Git LFS for large files
- ❌ **Don't ignore merge conflicts** - Resolve them carefully

### Commit Message Best Practices

#### Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

#### Examples

```bash
# Good
git commit -m "feat(auth): implement two-factor authentication"
git commit -m "fix(login): resolve session timeout issue"
git commit -m "docs(readme): update installation instructions"
git commit -m "refactor(api): optimize database queries"
git commit -m "style(ui): improve button styling consistency"

# Bad
git commit -m "fixed bug"
git commit -m "updates"
git commit -m "WIP"
git commit -m "asdfgh"
```

#### Commit Types

| Type | Purpose |
|------|---------|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation |
| `style` | Code style (formatting) |
| `refactor` | Code refactoring |
| `perf` | Performance improvement |
| `test` | Adding tests |
| `chore` | Build tools, dependencies |

### .gitignore Best Practices

```bash
# Node.js
node_modules/
.npm
package-lock.json

# Python
__pycache__/
*.py[cod]
*.egg-info/
.venv/

# IDE
.vscode/
.idea/
*.swp

# Environment
.env
.env.local

# OS
.DS_Store
Thumbs.db
```

---

## 🎯 Quick Reference

### Status Check
```bash
git status                    # Current state
git log --oneline -5          # Last 5 commits
git branch                    # List branches
```

### Before Pushing
```bash
git pull                      # Get latest
git diff origin/main          # Review changes
git log origin/main..HEAD     # Commits to push
```

### Emergency Commands
```bash
git reflog                    # Recovery log
git reset --hard ORIG_HEAD    # Undo failed merge
git fsck --lost-found         # Find lost commits
```

---

## 📚 Additional Resources

- **Official Git Docs:** https://git-scm.com/doc
- **GitHub Guides:** https://guides.github.com
- **GitLab Best Practices:** https://docs.gitlab.com
- **Git Workflow:** https://www.atlassian.com/git

---

**Last Updated:** January 31, 2026

**Difficulty Levels:** Beginner ⭐ | Intermediate ⭐⭐ | Advanced ⭐⭐⭐

---

*This guide covers essential Git commands for professional development. Regular practice with these commands will significantly improve your development workflow and team collaboration.*
