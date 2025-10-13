# 🧰 Essential Git Words and Commands

This document lists the **common Git terms** and **commands** you’ll use during daily development work —  
especially when applying the **Git Flow branching model**.

---

## 📘 Common Git Terms (Words)

| **Term** | **Meaning / Use** |
|-----------|------------------|
| **Repository (repo)** | A folder or project tracked by Git that contains all your code and history. |
| **Commit** | A saved snapshot of your project’s current state. |
| **Branch** | A separate line of development that allows you to work without affecting other code. |
| **Merge** | Combines changes from one branch into another. |
| **Clone** | Download a remote repository to your local machine. |
| **Pull** | Fetch and merge changes from the remote repository into your local one. |
| **Push** | Upload your local commits to the remote repository. |
| **Remote** | A reference to a repository hosted online (e.g., GitHub). |
| **Origin** | The default name for your remote repository. |
| **HEAD** | A pointer showing your current position (branch or commit) in the repository. |
| **Staging area (index)** | Where changes are prepared before committing them. |
| **Conflict** | Occurs when two branches change the same code — Git needs help resolving it. |
| **Tag** | A label for a specific commit, often used for marking releases (e.g., `v1.0.0`). |
| **Pull Request (PR)** | A request to merge your branch into another one, often reviewed by teammates. |
| **Issue** | A task, bug, or feature request tracked in a project (like on GitHub). |
| **Fork** | A copy of another person’s repository under your account (used in open-source). |
| **Fetch** | Downloads the latest changes from a remote repository **without merging** them. |
| **Rebase** | Reapplies commits on top of another branch to create a linear history (alternative to merge). |
| **Checkout** | Switch between branches or restore files from a specific commit. |
| **Diff** | Shows differences between commits, branches, or working directory changes. |
| **Init** | Initializes a new Git repository in a folder (`git init`). |
| **Status** | Displays which files are modified, staged, or untracked. |
| **Log** | Displays a history of commits. |
| **Blame** | Shows who last modified each line in a file. |
| **Revert** | Creates a new commit that undoes the changes from a previous commit. |
| **Reset** | Moves the HEAD and optionally changes the staging area and working directory. |
| **Ignore (`.gitignore`)** | A file that tells Git which files or folders to exclude from tracking. |
| **Submodule** | A repository nested inside another repository (used for dependencies). |
| **Bare Repository** | A repo without a working directory, used mainly as a central remote (e.g., on servers). |
| **Detached HEAD** | A state where HEAD points to a specific commit instead of a branch. |
| **Cherry-pick** | Apply a specific commit from one branch onto another. |
| **Squash** | Combine multiple commits into a single one (used to clean up history before merging). |
| **Stash** | Temporarily saves uncommitted changes so you can switch branches safely. |
| **Tracking branch** | A local branch connected to a remote branch to sync automatically (`git pull`, `git push`). |
| **Workflow** | The strategy for how branches and commits are organized (e.g., Git Flow, GitHub Flow). |
| **Pipeline (CI/CD)** | Automated steps that test, build, and deploy code when changes are pushed. |


---

## 🧠 Tips for Using This Table

- If you’re learning Git deeply, memorize the **first 15–20 terms** — they’re the most common in real-world projects.  
- The rest (like `rebase`, `cherry-pick`, `stash`) are **advanced but very useful** once you’re comfortable.  


## ⚙️ Basic Git Commands

### 🔹 Initialize a repository
```bash
git init
```
Create a new Git repository in your current folder.

### 🔹 Clone a repository
```bash
git clone <repository-url>
```
Download a copy of an existing remote repository.

### 🔹 Check current status
```bash
git status
```
Show which files are modified, staged, or untracked.

### 🔹 Stage files for commit
```bash
git add <file-name>
# or to add everything:
git add .
```

### 🔹 Commit changes
```bash
git commit -m "Describe your changes"
```
Saves the staged changes to your local repository.

### 🔹 View commit history
```bash
git log
```

### 🔹 Push changes to remote
```bash
git push origin <branch-name>
```

### 🔹 Pull changes from remote
```bash
git pull
```
Fetch and merge the latest updates from your remote branch.

### 🔹 Switch branches
```bash
git checkout <branch-name>
```

### 🔹 Create a new branch
```bash
git checkout -b <branch-name>
```

### 🔹 Merge branches
```bash
git merge <branch-name>
```

---

## 🚀 Git Flow Commands

Initialize Git Flow in your project:
```bash
git flow init
```

### 🔹 Feature Branches
```bash
git flow feature start <feature-name>
git flow feature publish <feature-name>
git flow feature finish <feature-name>
```

### 🔹 Release Branches
```bash
git flow release start <version>
git flow release publish <version>
git flow release finish <version>
```

### 🔹 Hotfix Branches
```bash
git flow hotfix start <version>
git flow hotfix publish <version>
git flow hotfix finish <version>
```

---

## 🧠 Helpful Git Commands

### Undo last commit (keep changes)
```bash
git reset --soft HEAD~1
```

### Discard local changes (dangerous)
```bash
git checkout -- <file>
```

### See branch list
```bash
git branch
```

### Delete a branch
```bash
git branch -d <branch-name>
```

### Rename a branch
```bash
git branch -m <new-name>
```

### Fetch latest changes (without merging)
```bash
git fetch
```

### Check differences between commits or branches
```bash
git diff
```

---

## 🧭 Workflow Example (Summary)

```bash
# 1. Update local repo
git pull origin develop

# 2. Create a new feature branch
git flow feature start add-login

# 3. Work and commit changes
git add .
git commit -m "Add login functionality"

# 4. Push your branch to remote
git flow feature publish add-login

# 5. Create a Pull Request (PR) on GitHub
#    → Review → Approve → Merge into develop

# 6. Finish the feature (merge & delete branch)
git flow feature finish add-login
```

---

## 💡 Tips

- Always **pull** before starting new work.  
- Write **clear commit messages**.  
- Never push directly to `main`.  
- Use **branches** for every feature, bug, or fix.  
- Regularly check your status with `git status`.  

---

## 🏁 Final Note

> Git is powerful — but mastering these basic commands and flows will make your work smooth, organized, and professional.  
> Keep this file as your personal **Git reference guide** in your project.
