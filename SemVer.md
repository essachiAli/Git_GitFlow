## 🔖 Tags and Semantic Versioning (SemVer)

### 🧩 Definition
**Tags** in Git are labels assigned to specific commits to mark important points in the repository’s history, such as releases or hotfixes.  

**Semantic Versioning (SemVer)** is a standard format for version numbers:

```
MAJOR.MINOR.PATCH
```

- **MAJOR**: Increases for incompatible changes or major updates.  
- **MINOR**: Increases for new features that are backward-compatible.  
- **PATCH**: Increases for bug fixes or small changes.  

---

### ⚙️ How It Works in Git Flow
1. **Release branch** finished and merged into `main`:
```bash
git flow release finish v1.2.0
```
- Creates a tag `v1.2.0` on the merge commit.

2. **Hotfix branch** finished and merged into `main` and `develop`:
```bash
git flow hotfix finish v1.2.1
```
- Creates a tag `v1.2.1` on the commit with the hotfix.

---

### 🎯 Purpose of Tags with SemVer
- **Track releases**: Easily return to a specific version.  
- **Deploy easily**: Deployment systems can reference exact tags.  
- **Communicate changes**: SemVer shows if the update is major, minor, or a patch.  
- **Collaborate efficiently**: Teams coordinate around tagged versions.

---

### 🧠 Summary
> Tags using **Semantic Versioning (SemVer)** are created automatically with each release or hotfix in Git Flow.  
> They mark specific commits with meaningful version numbers, making it easy to track, deploy, and manage project versions.
