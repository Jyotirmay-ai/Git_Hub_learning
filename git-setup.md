## Git Version Control Setup

If you want to track this project with Git and push to GitHub, run the following commands inside the project folder:

```bash
# 1. Start tracking the project
git init

# 2. Add all your files (the .gitignore will leave out the virtual environments)
git add .

# 3. Create the first commit
git commit -m "Initial commit: Completed project"

# 4. Connect to your empty GitHub repository and push (Replace the URL below!)
git remote add origin https://github.com/your-username/your-repo-name.git
git branch -M main
git push -u origin main
```

## How to Save and Upload Future Changes

### 1. Stage the Change (add)
This prepares your modified files to be included in the next "snapshot."

```bash
git add .
```
> **Note:** Using the dot `.` adds all modified files. If you only changed one file, you can use `git add filename.py`.

### 2. Record the Change (commit)
This saves the snapshot to your local history with a message explaining what you did.

```bash
git commit -m "Fixed the login bug"
```
> **Tip:** Keep your messages short and descriptive. Since you're a CSE student, getting into the habit of clear commit messages makes your GitHub profile look very professional to recruiters.

### 3. Upload the Change (push)
This moves your local commit up to the GitHub servers.

```bash
git push
```
