**Git Best Practices Configuration & Workflow Cheat Sheet**

---

**1. Set Your Identity (Required)**
```bash
git config --global user.name "Huzaif Rauf Tarazi"
git config --global user.email "your-email@example.com"
```
- Links commits to your GitHub account.
- Use the same email as your GitHub account.

**2. Set Default Branch Name**
```bash
git config --global init.defaultBranch main
```
- Ensures new repositories start with `main` instead of `master`.

**3. Handle Line Endings (Windows)**
```bash
git config --global core.autocrlf true
```
- Converts line endings between Windows (CRLF) and Unix/Linux (LF).
- Prevents unnecessary changes in commits.

**4. Enable Colored Output**
```bash
git config --global color.ui auto
```
- Makes Git output easier to read with colors for staged, modified, and untracked files.

**5. Set Default Editor**
```bash
git config --global core.editor "code --wait"
```
- Sets VS Code as the default editor for commit messages.
- Replace with `nano` or `vim` if preferred.

**6. Create Useful Aliases**
```bash
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.cm commit
git config --global alias.br branch
```
- `git st` → `git status`
- `git co` → `git checkout`
- `git cm` → `git commit`
- `git br` → `git branch`
- Saves time and simplifies commands.

**7. Verify Configuration**
```bash
git config --global --list
```
- Lists all global settings to check if your configuration is correct.

---
**8. Initialize a Repository**
```bash
git init              # Initialize new Git repository
git init -b main      # Initialize with 'main' as default branch
```
- Always initialize Git in your project root.

**9. Stage and Commit Files**
```bash
git add <file>        # Stage a specific file
git add .             # Stage all changes
git commit -m "Your commit message"  # Commit staged changes
```
- Commit often with meaningful messages.
- Stage only what you want to include in a commit.

**10. Check Status and Log**
```bash
git status            # See untracked, staged, and modified files
git log --oneline --graph --all  # View commit history visually
```
- Helps track project progress and verify changes before committing.

**11. Revert or Reset Changes**
```bash
git revert <commit-hash>       # Undo a commit safely by creating a new commit
git reset --soft <commit-hash>  # Move HEAD to a previous commit, keep changes staged
git reset --mixed <commit-hash> # Move HEAD, keep changes unstaged (default)
git reset --hard <commit-hash>  # Move HEAD and delete changes (use carefully)
```
- `git revert` is safe for shared/public repos.
- Use `git reset` carefully; `--hard` deletes changes permanently.

**12. Delete Files from Git but Keep Locally**
```bash
git rm --cached <file>  # Stop tracking a file already committed
```
- Useful for adding files to `.gitignore` that were already tracked.

**13. Branching Concept (Simple Explanation)**

A **branch** in Git is an independent line of development. It allows you to work on a feature, bug fix, or experiment **without affecting the main (stable) codebase**.

- `main` (or `master`) is usually the **stable production branch**.
- Feature work should be done in **separate branches**.
- Branches help teams work **in parallel** safely.

Think of branches like **copies of your project timeline** where you can safely make changes and later combine them.

---

**14. What Is a Merge Conflict?**

A **merge conflict** happens when Git cannot automatically combine changes from two branches.

This usually occurs when:
- Two branches modify the **same file**
- The **same line of code** is changed differently
- One branch deletes a line while another modifies it

Git stops and asks the developer to decide **what the final code should be**.

---

**15. The 3 Conflict Resolution Options Git Gives (Conceptual)**

When a conflict occurs, Git conceptually gives you **three choices**:

1. **Keep Current Changes**  
   - Keep the code from the branch you are currently on
   - Ignore incoming changes

2. **Accept Incoming Changes**  
   - Accept the changes from the branch being merged in
   - Discard current branch changes for that part

3. **Manually Merge Both Changes** (Best Practice)  
   - Review both versions
   - Combine the correct parts from each
   - This is the most common and professional approach

---

**16. Essential Branching Commands**
```bash
git branch                    # List all local branches
git branch <branch-name>       # Create a new branch
git checkout <branch-name>     # Switch to an existing branch
git checkout -b <branch-name>  # Create and switch to a new branch
git branch -d <branch-name>    # Delete a merged local branch
git branch -D <branch-name>    # Force delete a local branch (use carefully)
```
- Always work on features in a separate branch.
- Delete branches after successful merge to keep the repo clean.

---

**17. Types of Merges**

**Fast-Forward Merge**
- Happens when the `main` branch has no new commits since the feature branch was created.
- Git simply moves the branch pointer forward.
- No new merge commit is created.
- Clean and linear history.

**Three-Way Merge (Normal Merge)**
- Happens when both branches have diverged.
- Git creates a new merge commit combining both histories.
- Common in real-world team workflows.

---

**18. Essential Merge Commands & Best Practices**
```bash
git merge <branch-name>                 # Merge a branch into the current branch
git merge --no-ff <branch-name>          # Force a merge commit (no fast-forward)
git merge --abort                        # Cancel an ongoing merge (if conflicts occur)
```

**What These Mean (Simply):**
- `git merge <branch>`: Combines another branch into your current branch.
- `--no-ff`: Always creates a merge commit, even if fast-forward is possible (good for clear history).
- `git merge --abort`: Safely stops the merge and returns to the pre-merge state.

**Merge Best Practices:**
- Always switch to `main` (or target branch) before merging.
- Pull the latest changes before merging.
- Resolve conflicts manually and review code carefully.
- Prefer `--no-ff` for team projects to preserve context.
- Test the application after merging.


---

**18. Deleting Branches (Best Practices)**
```bash
git branch -d <branch-name>    # Delete branch after merge
git branch -D <branch-name>    # Force delete branch (if not merged)
```
- Never delete a branch before merging important work.
- Use force delete only when you are sure the branch is no longer needed.

---

**19. Git Stash (Temporary Save Work)**

**What is Stashing?**
- Git stash temporarily saves uncommitted changes.
- Useful when you need to switch branches quickly without committing.

**Stash Commands**
```bash
git stash              # Save current changes
git stash list         # View all stashes
git stash apply        # Reapply last stash (keeps stash)
git stash pop          # Reapply last stash and remove it
git stash drop         # Delete a stash
git stash clear        # Delete all stashes
```

**Stash Best Practices**
- Use stash for short-term work only.
- Do not rely on stash as long-term storage.
- Always review changes after applying a stash.

---

**20. Branching Best Practices (Final)**
- Keep `main` always stable and deployable.
- Create a new branch for each feature or fix.
- Prefer fast-forward merges when possible.
- Resolve conflicts manually and carefully.
- Delete branches after they are merged.



**14. Connecting Local Repository to GitHub (Remote Setup)**

**What does this mean?**  
A *local repository* lives on your computer. A *remote repository* lives on GitHub. To sync them, you must connect your local repo to GitHub using a **remote URL**.

```bash
git remote add origin https://github.com/USERNAME/REPOSITORY.git
```
- `origin` is the default name for the remote GitHub repository
- This command is done **once per project**

Verify connection:
```bash
git remote -v
```

---

**15. Push and Pull (Proper Usage & Meaning)**

**What is Git Push?**  
Push sends your *local commits* to GitHub.

```bash
git push -u origin main   # First-time push
```
- `-u` links your local `main` branch with GitHub
- After this, you can simply use:
```bash
git push
```

**What is Git Pull?**  
Pull downloads new commits from GitHub and merges them into your local branch.

```bash
git pull origin main
```

**Best Practice Order:**
1. `git pull`
2. Make changes
3. `git add` → `git commit`
4. `git push`

- Always pull before pushing to avoid conflicts
- Never push broken or untested code


**15. Overall Best Practices**
- Commit small, meaningful changes frequently.
- Stage only relevant files.
- Pull before pushing.
- Use descriptive commit messages.
- Revert safely in shared repos; reset carefully.

---
**End of Git Configuration & Workflow Best Practices Cheat Sheet**


---

## 12. Overall Git Best Practices (Used by Professional Developers)

### General Workflow Best Practices
- Always pull the latest changes before starting new work
- Keep commits small, focused, and meaningful
- Write clear, descriptive commit messages
- Commit logically complete work, not half-done code
- Avoid committing generated files, secrets, or credentials
- Use branches for every feature, bug fix, or experiment
- Merge frequently to avoid large conflicts
- Review changes before committing using `git status` and `git diff`
- Never work directly on `main` or `master` in team environments
- Push code regularly to avoid local data loss

### Commit Message Best Practices
- Use present tense ("Add login validation")
- Keep the first line under 50 characters
- Be specific about *what* and *why*
- Avoid vague messages like "fix" or "update"

### Branching Best Practices
- Use meaningful branch names (feature/login, bugfix/header)
- Delete branches after merging
- Keep branches short-lived
- Rebase or merge frequently with the main branch

### Merge Best Practices
- Resolve conflicts locally, never rush
- Test the application after every merge
- Prefer fast-forward merges for linear history
- Use merge commits when context matters

### Safety Best Practices
- Check logs before resetting or reverting
- Prefer `git revert` over `git reset` for shared branches
- Never force-push (`--force`) unless absolutely necessary
- Keep backups using remote repositories (GitHub)

---

## 13. Most Commonly Used Git Commands (Daily Developer Usage)

### Configuration & Setup
- `git config --global user.name "Your Name"`
- `git config --global user.email "you@email.com"`
- `git config --list`

### Repository Initialization
- `git init`
- `git clone <repository-url>`

### Daily Workflow Commands
- `git status`
- `git add .`
- `git add <file>`
- `git commit -m "message"`
- `git pull`
- `git push`

### Inspecting History
- `git log`
- `git log --oneline`
- `git diff`

### Branching
- `git branch`
- `git branch <branch-name>`
- `git checkout <branch>`
- `git checkout -b <branch>`
- `git merge <branch>`
- `git branch -d <branch>`

### Undo & Recovery
- `git restore <file>`
- `git revert <commit>`
- `git reset --soft <commit>`
- `git reset --mixed <commit>`
- `git reset --hard <commit>`

### Stashing
- `git stash`
- `git stash list`
- `git stash apply`
- `git stash drop`

### Cleanup & Maintenance
- `git clean -f`
- `git fetch --prune`

---

## 14. Final Professional Advice

Git is not just a tool—it is a **safety system** for your code. Developers who master Git:
- Make fewer mistakes
- Recover faster from errors
- Collaborate efficiently
- Maintain clean project history

Focus on understanding *why* each command is used, not just memorizing syntax. Mastery comes from consistent, disciplined usage.

