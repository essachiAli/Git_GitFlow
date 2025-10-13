# 🔄 Standard Flow Scenario — Issue → Feature → PR → Merge

## 🧩 Overview

This section explains the **standard development workflow** used alongside the **Git Flow model**.  
It shows how a task moves from an **idea or issue** to a **merged feature** in the main project.  
This process helps keep the workflow organized, encourages collaboration, and ensures code quality.

---

## 🎬 Scenario Example

Let’s imagine our team wants to **add a login system** to our project.

Here’s how the complete flow looks step-by-step 👇

---

### 1. 🪲 Create an Issue

Everything starts with an **issue** — a task, bug, or new feature request.

- We create an issue named:  
  **“Add user login system”**
- The issue includes:
  - Description of what needs to be done  
  - Expected behavior  
  - Assigned developer  

✅ **Goal:** Define *what* needs to be done and *why*.

---

### 2. 🌿 Create a Feature Branch

Once the issue is ready, the developer creates a **feature branch** to work on it.  
This branch is isolated from the main codebase, so development doesn’t affect production.

```bash
git flow feature start add-login-system
```

This creates a new branch:
```
feature/add-login-system
```

The developer can now code, commit changes, and test locally.

✅ **Goal:** Work safely and independently on the feature without breaking the main project.

---

### 3. 🔁 Open a Pull Request (PR)

After finishing the work, the developer **pushes** the feature branch to the remote repository and opens a **Pull Request (PR)**.

```bash
git push origin feature/add-login-system
```

Then, on GitHub (or GitLab), create a **Pull Request** from  
`feature/add-login-system` → `develop`.

The PR allows:
- Code review by other developers  
- Automated testing (CI/CD)  
- Discussion or requested changes  

✅ **Goal:** Review and validate the code before it enters the main branch.

---

### 4. ✅ Merge the Pull Request

Once the Pull Request is approved and tests pass, the feature branch is **merged** into `develop`.

```bash
git flow feature finish add-login-system
```

Git Flow will:
- Merge `feature/add-login-system` into `develop`  
- Delete the feature branch locally  

✅ **Goal:** Integrate the finished feature into the main development branch cleanly.

---

## 📊 Summary of the Flow

| **Step** | **Branch/Action** | **Description** |
|-----------|------------------|-----------------|
| **1. Issue** | Create an issue | Define the task or problem to solve |
| **2. Feature** | `feature/<feature-name>` | Develop and test the new code |
| **3. Pull Request (PR)** | Submit for review | Collaborate and ensure quality |
| **4. Merge** | Merge into `develop` | Integrate the feature after approval |

---

## 🧭 Example Diagram (Text Representation)

```
[ Issue: Add login system ]
        ↓
[ feature/add-login-system ]  ← developer codes the feature
        ↓
[ Pull Request created → develop ]
        ↓
[ Review + tests + approval ]
        ↓
[ Merge → develop ]
        ↓
[ Feature branch deleted ]
```

---

## 💡 Notes & Best Practices

- Always link the **PR** to the **issue** (so they’re connected).  
- Use **clear branch names**, e.g., `feature/add-login-system`.  
- Keep your commits small and meaningful.  
- Always pull the latest `develop` branch before starting new work.  
- Never push directly to `main` — use branches and PRs.  

---

## 🏁 Final Summary

> **In short:**  
> The flow `issue → feature → PR → merge` keeps the project organized and collaborative.  
> Every change starts as a tracked issue, gets built safely in a feature branch, reviewed through a PR, and finally merged into `develop` for the next release.

---

This scenario ensures that anyone (including your future self 👀) can clearly understand how to move from **idea → code → release** using Git Flow and GitHub.
