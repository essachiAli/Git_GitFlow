# Git Flow Branching Model

This repository uses the **Git Flow branching model** to manage development workflows.  
Git Flow is a structured approach to branching and merging that ensures a clean and organized commit history.  
Below is an explanation of the process and commands.

---

## Overview

Git Flow organizes branches into specific roles:

- **main**: The production-ready branch, containing stable code.  
- **develop**: The integration branch for ongoing development, containing the latest work.  
- **feature/***: Branches for developing new features, branched from `develop`.  
- **release/***: Branches for preparing a release, branched from `develop` and merged into `main` and `develop`.  
- **hotfix/***: Branches for urgent fixes, branched from `main` and merged back into `main` and `develop`.  
- **support/***: Branches for long-term support of older releases, branched from `main`.

---

## Setup

To initialize Git Flow in your repository:

```bash
git flow init
```

Follow the prompts to set branch names (e.g., `main` for production, `develop` for development).  
Use the following command to accept default settings:

```bash
git flow init -d
```

---

## Common Commands

### Feature Branches

For new features or changes:

**Start a feature:**
```bash
git flow feature start <feature-name>
```
Creates a branch `feature/<feature-name>` from `develop`.

**Finish a feature:**
```bash
git flow feature finish <feature-name>
```
Merges the feature into `develop` and deletes the feature branch.

**Publish to remote:**
```bash
git flow feature publish <feature-name>
```

**Pull from remote:**
```bash
git flow feature pull <remote> <feature-name>
```

---

### Release Branches

To prepare a new release:

**Start a release:**
```bash
git flow release start <release-version>
```
Creates a branch `release/<release-version>` from `develop`.

**Finish a release:**
```bash
git flow release finish <release-version>
```
Merges into `main` and `develop`, tags the release, and deletes the release branch.

---

### Hotfix Branches

For urgent fixes to production:

**Start a hotfix:**
```bash
git flow hotfix start <hotfix-version>
```
Creates a branch `hotfix/<hotfix-version>` from `main`.

**Finish a hotfix:**
```bash
git flow hotfix finish <hotfix-version>
```
Merges into `main` and `develop`, tags the hotfix, and deletes the hotfix branch.

---

### Support Branches

For maintaining older releases:

**Start a support branch:**
```bash
git flow support start <release-version> <base-commit>
```
Creates a branch `support/<release-version>` from a commit on `main`.

---

## Installation

To use Git Flow, install the `git-flow` tool:

**On macOS:**
```bash
brew install git-flow
```

**On Linux:**
```bash
sudo apt-get install git-flow
```

**On Windows:**  
Use a package manager like Chocolatey or download from the [Git Flow repo](https://github.com/nvie/gitflow).

For detailed installation instructions, see the **Git Flow Wiki**.

---

## Best Practices

- Always branch features from `develop`, not `main`.  
- Keep feature branches focused on a single change.  
- Regularly merge `develop` into feature branches to stay updated.  
- Use descriptive branch names (e.g., `feature/add-user-auth`).  
- Tag releases and hotfixes for traceability.

---

## Resources

- **Original blog post:** [A Successful Git Branching Model](https://nvie.com/posts/a-successful-git-branching-model/)  
- **Git Flow repo:** [github.com/nvie/gitflow](https://github.com/nvie/gitflow)  
- **Community discussion:** [Google Group](https://groups.google.com/g/gitflow-users)

---

## License

Git Flow is licensed under the **BSD License**.  
See the LICENSE file for details.
