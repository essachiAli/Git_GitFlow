# 🧭 Contributing Guidelines

Welcome! 🎉  
This document explains how to contribute to this project and the **branching policy** we follow using the **Git Flow model**.

---

## 🌳 Branching Policy

Our workflow is based on the **Git Flow branching model**.  
Each branch type has a specific purpose and rules. Please follow these conventions carefully to keep the project clean and organized.

### 🔹 Main Branch (`main`)
- Represents **production-ready** code.  
- Always contains **stable, tested, and deployable** versions.  
- **Never commit directly** to `main`.  
- Only updated through:
  - `release/*` branches (for new releases)
  - `hotfix/*` branches (for urgent fixes)

---

### 🔹 Develop Branch (`develop`)
- The **integration branch** for ongoing development.  
- Contains the latest approved features before release.  
- All feature branches are **merged back** into `develop`.  
- The base branch for:
  - `feature/*` branches  
  - `release/*` branches

---

### 🔹 Feature Branches (`feature/*`)
- Used to develop new features or improvements.  
- Always branched **from** `develop`.  
- Merge back **into** `develop` when complete.  
- Naming convention:  
  ```
  feature/<short-feature-description>
  ```
  Example:  
  ```
  feature/add-login-page
  feature/update-navbar
  ```
- Commands:
  ```bash
  git flow feature start add-login-page
  git flow feature finish add-login-page
  ```

---

### 🔹 Release Branches (`release/*`)
- Used to prepare for a **new version** of the project.  
- Branched **from** `develop` when all planned features for a release are complete.  
- Allows testing, versioning, and documentation updates before going live.  
- Merged into both:
  - `main` → for production  
  - `develop` → to include release changes
- Commands:
  ```bash
  git flow release start v1.0.0
  git flow release finish v1.0.0
  ```

---

### 🔹 Hotfix Branches (`hotfix/*`)
- Used to fix **critical bugs** found in production.  
- Branched **from** `main`.  
- Merged into both:
  - `main` → to apply the fix immediately  
  - `develop` → to keep development updated  
- Commands:
  ```bash
  git flow hotfix start fix-login-bug
  git flow hotfix finish fix-login-bug
  ```

---

### 🔹 Support Branches (`support/*`)
- Used to maintain **older releases** that are still in use.  
- Branched from a previous release commit on `main`.  
- Rarely used unless long-term support is needed.

---

## 🧠 Workflow Summary

```
Issue → Feature Branch → Pull Request → Merge to Develop → Release → Main
```

Or visually:

```
main  ←── release/*  ←── develop  ←── feature/*
  ↑                        ↑
 hotfix/*              (new features)
```

---

## ✅ Contribution Rules

1. **Create an issue** before starting a new feature or bug fix.  
2. **Branch from `develop`** for new features.  
3. **Branch from `main`** for urgent hotfixes.  
4. Always **write clear commit messages**:
   ```
   [Feature] Add login functionality
   [Fix] Correct API endpoint for user data
   ```
5. **Open a Pull Request (PR)** to merge your branch.  
6. Wait for **review and approval** before merging.  
7. Keep your branch **updated** with the latest `develop` changes.  
   ```bash
   git pull origin develop
   ```
8. Delete branches after merging to keep the repository clean.

---

## 🧩 Example Git Flow

```bash
# Start a new feature
git flow feature start add-user-auth

# Work and commit your changes
git add .
git commit -m "Add user authentication system"

# Finish and merge the feature
git flow feature finish add-user-auth

# Start a release
git flow release start v1.0.0
git flow release finish v1.0.0
```

---

## 💡 Tips

- Do not work directly on `main` or `develop`.  
- Use **small, focused branches**.  
- Regularly **sync with remote** to avoid conflicts.  
- Tag releases properly using semantic versioning (`v1.0.0`, `v1.1.0`, etc.).  
- Use meaningful branch names and commit messages.

---

## 📜 License

By contributing, you agree that your contributions will be licensed under the project’s existing license.

---

## 🤝 Thank You

Your contributions help keep this project strong, organized, and professional.  
Welcome aboard 🚀

---

