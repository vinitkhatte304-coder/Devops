# 🔧 Git & GitHub Notes

## What is Git?

**Git** is a **Distributed Version Control System (DVCS)** used to track changes in source code during software development. It helps developers collaborate, manage different versions of code, and maintain a complete history of changes.

### Features

- Tracks code changes
- Supports collaboration among multiple developers
- Maintains version history
- Allows branching and merging
- Enables easy rollback to previous versions

---

# What is GitHub?

**GitHub** is a **cloud-based platform** that hosts Git repositories. It provides tools for version control, collaboration, code review, issue tracking, and project management.

### Features

- Cloud storage for Git repositories
- Team collaboration
- Pull Requests
- Issue Tracking
- GitHub Actions (CI/CD)
- Repository Management

---

# What is a Repository?

A **Repository (Repo)** is a storage location that contains:

- Source Code
- Project Files
- Documentation
- Commit History
- Branches

A repository keeps track of every change made to a project.

### Types of Repositories

- **Local Repository** – Stored on your computer.
- **Remote Repository** – Hosted on platforms like GitHub.

---

# What is a GitHub Token?

A **GitHub Personal Access Token (PAT)** is a secure authentication key that allows your computer or applications to access your GitHub account without using your account password.

### Why Use a Token?

- More secure than passwords
- Required for HTTPS authentication
- Can be revoked anytime
- Supports fine-grained permissions

---

# Git Configuration Commands

Before using Git, configure your username and email.

## Set Username

```bash
git config --global user.name "Your Name"
```

Example

```bash
git config --global user.name "Vinit Khatte"
```

---

## Set Email

```bash
git config --global user.email "your@email.com"
```

Example

```bash
git config --global user.email "vinit@example.com"
```

---

## View All Git Configurations

```bash
git config --list
```

---

## View Configured Username

```bash
git config user.name
```

---

## View Configured Email

```bash
git config user.email
```

---

# Basic Git Workflow

## Check Repository Status

```bash
git status
```

Shows the current state of your working directory.

---

## Add All Files

```bash
git add .
```

Stages all modified and new files.

---

## Commit Changes

```bash
git commit -m "Your commit message"
```

Example

```bash
git commit -m "Added networking notes"
```

---

## Remove Existing Remote

```bash
git remote remove origin
```

Removes the current remote repository.

---

## Add New Remote Repository

```bash
git remote add origin <repository-url>
```

Example

```bash
git remote add origin https://github.com/username/project.git
```

---

## Push Code to GitHub

```bash
git push origin main
```

or

```bash
git push origin master
```

Uploads your local commits to the remote repository.

---

## Pull Latest Changes

```bash
git pull origin master --rebase
```

or

```bash
git pull origin main --rebase
```

Downloads the latest changes from the remote repository and reapplies your local commits on top.

---

# Branch Commands

## Create a New Branch

```bash
git branch branch-name
```

Example

```bash
git branch feature-login
```

---

## View All Branches

```bash
git branch
```

Shows all local branches.

---

## Switch to Another Branch

```bash
git checkout branch-name
```

Example

```bash
git checkout feature-login
```

---

## Create and Switch to a New Branch

```bash
git checkout -b branch-name
```

Example

```bash
git checkout -b feature-payment
```

---

## Delete a Local Branch

```bash
git branch -d branch-name
```

Example

```bash
git branch -d feature-login
```

---

## Delete a Remote Branch

```bash
git push origin --delete branch-name
```

Example

```bash
git push origin --delete feature-login
```

---

# Common Git Commands

| Command | Description |
|----------|-------------|
| `git init` | Initialize a new Git repository |
| `git clone <repo-url>` | Clone a remote repository |
| `git status` | Check repository status |
| `git add .` | Stage all changes |
| `git commit -m "message"` | Save changes locally |
| `git log` | View commit history |
| `git diff` | View file differences |
| `git branch` | List branches |
| `git checkout branch-name` | Switch branch |
| `git checkout -b branch-name` | Create and switch branch |
| `git merge branch-name` | Merge another branch |
| `git pull origin main` | Download latest changes |
| `git push origin main` | Upload changes to GitHub |
| `git remote -v` | View remote repositories |
| `git remote add origin <url>` | Add remote repository |
| `git remote remove origin` | Remove remote repository |

---

# Git Workflow

```text
Create Project
      │
      ▼
git init
      │
      ▼
Create Files
      │
      ▼
git status
      │
      ▼
git add .
      │
      ▼
git commit -m "Initial Commit"
      │
      ▼
git remote add origin <repo-url>
      │
      ▼
git push origin main
```

---

# Difference Between Git and GitHub

| Git | GitHub |
|-----|--------|
| Version Control System | Cloud Hosting Platform |
| Works Locally | Works Online |
| Tracks Code Changes | Stores Git Repositories |
| Open Source Tool | Web-based Service |
| No Internet Required | Internet Required |

---

# Quick Interview Revision

## Git

- Distributed Version Control System
- Tracks code changes
- Supports branching and merging

---

## GitHub

- Cloud platform for hosting Git repositories
- Enables collaboration and code sharing

---

## Repository

- Storage location for source code and version history

---

## GitHub Token

- Secure authentication key
- Replaces passwords for Git operations

---

## Frequently Used Commands

```bash
git init
git clone <url>
git status
git add .
git commit -m "message"
git push origin main
git pull origin main
git branch
git checkout branch-name
git checkout -b branch-name
git merge branch-name
git log
git remote -v
```

---

# Author

**Prepared by:** Vinit Khatte  
**Purpose:** AWS • DevOps • Git & GitHub Interview Revision Notes
