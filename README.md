<div align="center">

# 🚀 Git & GitHub Commands Cheatsheet

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com)
[![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)](https://git-scm.com/)

**A comprehensive Git & GitHub commands reference with examples - Your complete cheatsheet for version control**

[📖 Documentation](https://git-scm.com/doc) | [💡 Contribute](https://github.com/iNSRawat/git-github-cheatsheet/issues) | [⭐ Star this repo](https://github.com/iNSRawat/git-github-cheatsheet)

</div>

---

## 📑 Table of Contents

- [Getting Started](#getting-started)
- [Configuration](#configuration)
- [Basic Commands](#basic-commands)
- [Branching & Merging](#branching--merging)
- [Viewing History](#viewing-history)
- [Undoing Changes](#undoing-changes)
- [Stashing](#stashing)
- [Remote Repositories](#remote-repositories)
- [Tags & Releases](#tags--releases)
- [Advanced Commands](#advanced-commands)
- [GitHub Specific](#github-specific)

---

## 🎯 Getting Started

### Initialize a New Repository
```bash
git init
# Initialize a new local git repository
```

### Clone an Existing Repository
```bash
git clone https://github.com/username/repository.git
# Clone via HTTPS

git clone git@github.com:username/repository.git
# Clone via SSH

git clone https://github.com/username/repository.git my-folder
# Clone into a specific folder
```

---

## ⚙️ Configuration

### Set User Information
```bash
git config --global user.name "Your Name"
# Set your name globally

git config --global user.email "you@example.com"
# Set your email globally

git config user.name "Your Name"
# Set name for current repository only
```

### View Configuration
```bash
git config --list
# List all configurations

git config user.name
# Show specific configuration

git config --global --edit
# Edit global config file
```

### Set Default Branch
```bash
git config --global init.defaultBranch main
# Set default branch name to 'main'
```

### Set Default Editor
```bash
git config --global core.editor "code --wait"
# Set VS Code as default editor

git config --global core.editor "vim"
# Set Vim as default editor
```

---

## 💻 Basic Commands

### Check Status
```bash
git status
# Show working tree status

git status -s
# Short format status
```

### Adding Files
```bash
git add filename.txt
# Stage a specific file

git add .
# Stage all changes in current directory

git add -A
# Stage all changes in entire repository

git add *.js
# Stage all JavaScript files

git add -p
# Interactive staging
```

### Committing
```bash
git commit -m "Commit message"
# Commit staged changes

git commit -am "Commit message"
# Stage and commit tracked files

git commit --amend
# Modify last commit

git commit --amend --no-edit
# Amend without changing message
```

### Removing & Renaming
```bash
git rm filename.txt
# Remove file and stage deletion

git rm --cached filename.txt
# Remove from staging, keep locally

git mv oldname.txt newname.txt
# Rename or move a file
```

---

## 🌿 Branching & Merging

### List Branches
```bash
git branch
# List local branches

git branch -r
# List remote branches

git branch -a
# List all branches

git branch -v
# List with last commit
```

### Create & Switch Branch
```bash
git branch new-branch
# Create new branch

git checkout branch-name
# Switch to branch

git switch branch-name
# Switch (newer syntax)

git checkout -b new-branch
# Create and switch

git switch -c new-branch
# Create and switch (newer)
```

### Rename & Delete Branch
```bash
git branch -m old-name new-name
# Rename branch

git branch -d branch-name
# Delete merged branch

git branch -D branch-name
# Force delete branch

git push origin --delete branch-name
# Delete remote branch
```

### Merge Branches
```bash
git merge branch-name
# Merge into current branch

git merge --no-ff branch-name
# Merge with commit

git merge --squash branch-name
# Squash commits
```

### Rebase
```bash
git rebase main
# Rebase onto main

git rebase -i HEAD~3
# Interactive rebase

git rebase --continue
# Continue after conflict

git rebase --abort
# Cancel rebase
```

---

## 📜 Viewing History

### View Commits
```bash
git log
# Show commit history

git log --oneline
# Compact format

git log --graph --all
# Visual graph

git log -n 5
# Last 5 commits

git log --since="2 weeks ago"
# Recent commits

git log --author="Name"
# By author

git log --grep="bug"
# Search commits

git log filename
# File history

git log --stat
# Show stats
```

### Show Details
```bash
git show commit-hash
# Show commit details

git show HEAD
# Latest commit

git show HEAD~2
# 2 commits before

git diff
# Show unstaged changes

git diff --staged
# Show staged changes

git diff branch1 branch2
# Compare branches
```

### Blame & Bisect
```bash
git blame filename
# Show line authors

git bisect start
# Find bug commit

git bisect bad
# Mark bad commit

git bisect good commit-hash
# Mark good commit
```

---

## ↩️ Undoing Changes

### Discard Changes
```bash
git checkout -- filename
# Discard file changes

git restore filename
# Restore file (newer)

git restore .
# Restore all files
```

### Unstage Files
```bash
git reset filename
# Unstage file

git restore --staged filename
# Unstage (newer)
```

### Reset Commits
```bash
git reset --soft HEAD~1
# Undo commit, keep staged

git reset --mixed HEAD~1
# Undo commit, keep unstaged

git reset --hard HEAD~1
# Undo commit, discard all

git reset --hard origin/main
# Reset to remote
```

### Revert & Clean
```bash
git revert commit-hash
# Create undo commit

git clean -n
# Preview clean

git clean -f
# Remove untracked files

git clean -fd
# Remove files and directories
```

---

## 📦 Stashing

### Save Stash
```bash
git stash
# Stash changes

git stash save "Message"
# Stash with message

git stash -u
# Include untracked
```

### List & Apply
```bash
git stash list
# Show stashes

git stash show
# Show latest stash

git stash apply
# Apply latest stash

git stash apply stash@{2}
# Apply specific stash

git stash pop
# Apply and remove
```

### Manage Stashes
```bash
git stash drop stash@{0}
# Delete stash

git stash clear
# Delete all stashes

git stash branch new-branch
# Create branch from stash
```

---

## 🌐 Remote Repositories

### Add & View Remote
```bash
git remote add origin <url>
# Add remote

git remote -v
# List remotes with URLs

git remote show origin
# Show remote details
```

### Change Remote
```bash
git remote set-url origin <new-url>
# Change remote URL

git remote rename origin new-name
# Rename remote

git remote remove origin
# Remove remote
```

### Fetch, Pull & Push
```bash
git fetch
# Fetch from remote

git fetch --all
# Fetch from all remotes

git pull
# Fetch and merge

git pull --rebase
# Pull with rebase

git push
# Push to remote

git push -u origin main
# Push and set upstream

git push --all
# Push all branches

git push --tags
# Push all tags

git push --force-with-lease
# Safer force push
```

---

## 🏷️ Tags & Releases

### Create & List Tags
```bash
git tag
# List all tags

git tag v1.0
# Create lightweight tag

git tag -a v1.0 -m "Version 1.0"
# Create annotated tag

git tag v1.0 commit-hash
# Tag specific commit
```

### Push & Delete Tags
```bash
git push origin v1.0
# Push specific tag

git push origin --tags
# Push all tags

git tag -d v1.0
# Delete local tag

git push origin --delete v1.0
# Delete remote tag
```

---

## 🔧 Advanced Commands

### Cherry-pick
```bash
git cherry-pick commit-hash
# Apply commit to current branch

git cherry-pick commit1 commit2
# Pick multiple commits
```

### Reflog
```bash
git reflog
# Show reference log

git reset --hard HEAD@{2}
# Reset to reflog state
```

### Submodules
```bash
git submodule add <url> path
# Add submodule

git submodule init
# Initialize submodules

git submodule update
# Update submodules

git clone --recursive <url>
# Clone with submodules
```

### Archive
```bash
git archive --format=zip --output=project.zip main
# Create zip archive
```

---

## 🐙 GitHub Specific

### Fork Workflow
```bash
# 1. Fork on GitHub website
# 2. Clone your fork
git clone https://github.com/YOUR-USERNAME/repo.git

# 3. Add upstream remote
git remote add upstream https://github.com/ORIGINAL-OWNER/repo.git

# 4. Sync with upstream
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```

### Pull Request Workflow
```bash
# 1. Create feature branch
git checkout -b feature-branch

# 2. Make changes and commit
git add .
git commit -m "Add feature"

# 3. Push to your fork
git push origin feature-branch

# 4. Create PR on GitHub
# 5. After merge, cleanup
git checkout main
git pull upstream main
git branch -d feature-branch
git push origin --delete feature-branch
```

### GitHub CLI (gh)
```bash
gh repo clone username/repo
# Clone repository

gh repo create my-repo --public
# Create new repository

gh pr create --title "Fix bug"
# Create pull request

gh pr list
# List pull requests

gh issue create --title "Bug"
# Create issue

gh issue list
# List issues
```

---

<div align="center">

## 📚 Additional Resources

- [Official Git Documentation](https://git-scm.com/doc)
- [GitHub Docs](https://docs.github.com)
- [Pro Git Book](https://git-scm.com/book/en/v2)
- [Git Cheat Sheet PDF](https://education.github.com/git-cheat-sheet-education.pdf)

---

## 👤 Connect With Me

[![GitHub](https://img.shields.io/badge/GitHub-iNSRawat-181717?style=for-the-badge&logo=github)](https://github.com/iNSRawat)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=for-the-badge&logo=linkedin)](https://linkedin.com/in/insrawat)
[![Portfolio](https://img.shields.io/badge/Portfolio-Visit-FF5722?style=for-the-badge&logo=google-chrome&logoColor=white)](https://bio.link/nsrawat)

---

### ⭐ If you found this helpful, please star this repository!

**Made with ❤️ by [N S Rawat](https://github.com/iNSRawat)**

</div>
