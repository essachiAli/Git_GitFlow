# 🔥 The `hotfix` Branch in Git Flow

## Overview

In the **Git Flow** workflow, a `hotfix` branch is used to **quickly address critical issues or bugs** found in the production environment.  
These fixes are made directly from the `main` branch to minimize downtime and are then merged back into both `main` and `develop` to keep all branches up to date.

---

## 🔍 Key Characteristics

- **Created from:** `main`  
- **Merged into:** `main` and `develop`  
- **Purpose:** To fix urgent issues in the production release (e.g., security bugs, crash fixes)  
- **Naming convention:** `hotfix/<version>` (e.g., `hotfix/1.0.1`, `hotfix/2.2.3`)  
- **Temporary branch:** Deleted after merging and tagging the release  

---

## 🧭 Example Workflow

```bash
# Start a hotfix branch from main
git flow hotfix start 1.0.1

# (Optional) Publish the hotfix branch to remote
git flow hotfix publish 1.0.1

# Apply and commit the fix
git commit -am "Fix critical login issue in production"

# Finish the hotfix
git flow hotfix finish 1.0.1
```

### Explanation of Commands

- `git flow hotfix start <version>` → Creates a new branch `hotfix/<version>` from `main`.  
- `git flow hotfix publish <version>` → Pushes the hotfix branch to the remote repository for collaboration.  
- `git flow hotfix finish <version>` →  
  - Merges the fix into both `main` and `develop`.  
  - Tags the commit with the hotfix version (e.g., `v1.0.1`).  
  - Deletes the hotfix branch locally.

---

## ✅ Summary

| **Aspect** | **Description** |
|-------------|-----------------|
| **Branch name** | `hotfix/<version>` |
| **Source branch** | `main` |
| **Destination branches** | `main` and `develop` |
| **Purpose** | Quickly fix critical bugs in production |
| **Contains** | Emergency patches, urgent security or stability fixes |
| **Merged when** | The fix is tested and verified |
| **Deleted after merge** | ✅ Yes |

---

## 📊 Diagram (Text Representation)

```
main ────────────────┐
                      ├── hotfix/1.0.1
                      │     ├── fix → main (production)
                      │     └── merge → develop (sync fix)
develop ──────────────┘
```

---

The `hotfix` branch ensures production issues can be resolved immediately without interrupting ongoing development work in `develop`, maintaining both stability and productivity.
