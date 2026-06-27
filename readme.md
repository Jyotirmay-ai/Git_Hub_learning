# Git Cheat Sheet

This README is a simple guide you can use whenever you forget the basic Git commands.

## 1. Configure Git once
Set your name and email before your first commit:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --global init.defaultBranch main
```

## 2. Start a new Git project
Go to your project folder and initialize Git:

```bash
cd path/to/your/project
git init
```

## 3. Connect your project to GitHub
If you already created a repository on GitHub, connect it like this:

```bash
git remote add origin https://github.com/your-username/your-repo-name.git
git branch -M main
git push -u origin main
```

If the remote already exists, use:

```bash
git remote set-url origin https://github.com/your-username/your-repo-name.git
```

## 4. Save your work
The normal Git workflow is:

```bash
git status
git add .
git commit -m "Short descriptive message"
git push
```

### What each step means
- `git status`: shows what changed
- `git add .`: stages all modified files
- `git commit -m "..."`: saves the changes locally
- `git push`: uploads commits to GitHub

## 5. Check your history
To see previous commits:

```bash
git log --oneline --decorate --graph --all
```

## 6. Create and switch branches
Branches help you work on features safely:

```bash
git branch
git checkout -b feature-name
```

Modern Git also supports:

```bash
git switch -c feature-name
git switch main
```

To merge a branch back into main:

```bash
git checkout main
git merge feature-name
```

To delete a branch after merging:

```bash
git branch -d feature-name
```

## 7. Pull the latest changes
Before starting work, update your local repository:

```bash
git pull origin main
```

## 8. Undo or fix mistakes
Use these carefully:

```bash
# Undo changes in a file
 git restore filename.py

# Undo the last commit but keep the changes
 git reset --soft HEAD~1

# Undo the last commit and remove the changes
 git reset --hard HEAD~1
```

## 9. Start over with a fresh repository
If your Git history is corrupted or messy, you can reset it:

### PowerShell
```powershell
Remove-Item -Recurse -Force .git
```

### Bash
```bash
rm -rf .git
```

Then start fresh:

```bash
git init
git branch -M main
git remote add origin https://github.com/your-username/your-repo-name.git
git add .
git commit -m "initial CLI Version"
git tag v1.0.0
git push -u origin main --force
git push origin v1.0.0
```

## 10. Common Git problems
### “fatal: not a git repository”
Run:

```bash
git init
```

### “remote origin already exists”
Remove it and add again:

```bash
git remote remove origin
git remote add origin https://github.com/your-username/your-repo-name.git
```

### “Your branch is behind 'origin/main'”
Update it:

```bash
git pull --rebase origin main
```

## 11. Useful .gitignore tip
If you have virtual environments, cache files, or build output, add them to a `.gitignore` file so Git ignores them.

Example:

```gitignore
__pycache__/
.venv/
env/
dist/
build/
```

## 12. Quick summary
If you only remember one routine, remember this:

```bash
git status
git add .
git commit -m "Your message"
git push
```

That is the basic cycle of saving and uploading your work with Git.
