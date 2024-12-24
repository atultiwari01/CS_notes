# Git and GitHub Setup Guide

## Table of Contents
- [Introduction](#introduction)
- [Installing Git](#installing-git)
- [Configuring Git](#configuring-git)
- [Setting up GitHub](#setting-up-github)
- [Setting up VS Code](#setting-up-vs-code)
- [Basic Git Commands](#basic-git-commands)
- [Working with GitHub](#working-with-github)
- [Advanced Git Commands](#advanced-git-commands)

## Introduction

Git is a distributed version control system that helps track changes in source code during software development. GitHub is a web-based hosting service for Git repositories. This guide will help you set up both Git and GitHub, and integrate them with Visual Studio Code.

## Installing Git

### Windows
1. Download Git from [https://git-scm.com/download/windows](https://git-scm.com/download/windows)
2. Run the installer and follow the installation wizard

### macOS
Using Homebrew:
```bash
brew install git
```

### Linux (Ubuntu/Debian)
```bash
sudo apt-get update
sudo apt-get install git
```

## Configuring Git

After installation, configure your Git identity:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

To verify your configuration:
```bash
git config --list
```

## Setting up GitHub

1. Create a GitHub account at [https://github.com](https://github.com)
2. Set up SSH key for secure communication:

Generate SSH key:
```bash
ssh-keygen -t ed25519 -C "your.email@example.com"
```

Add SSH key to ssh-agent:
```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

Copy the public key:
- Windows:
```bash
cat ~/.ssh/id_ed25519.pub | clip
```
- macOS:
```bash
pbcopy < ~/.ssh/id_ed25519.pub
```
- Linux:
```bash
xclip -sel clip < ~/.ssh/id_ed25519.pub
```

3. Add the SSH key to your GitHub account in Settings > SSH and GPG keys

## Setting up VS Code

1. Install VS Code from [https://code.visualstudio.com](https://code.visualstudio.com)
2. Install recommended extensions:
   - GitLens
   - GitHub Pull Requests and Issues

## Basic Git Commands

### Initialize a Repository
```bash
git init
```

### Check Repository Status
```bash
git status
```

### Add Files to Staging Area
```bash
# Add specific file
git add filename.txt

# Add all files
git add .

# Add all files of a specific type
git add *.js
```

### Commit Changes
```bash
# Commit with message
git commit -m "Your commit message"

# Add and commit in one command
git commit -am "Your commit message"
```

### View Commit History
```bash
# View full history
git log

# View compact history
git log --oneline

# View graph of branches
git log --graph --oneline
```

## Working with GitHub

### Clone a Repository
```bash
git clone git@github.com:username/repository.git
```

### Connect Local Repository to GitHub
```bash
git remote add origin git@github.com:username/repository.git
```

### Push Changes
```bash
# First time push
git push -u origin main

# Subsequent pushes
git push
```

### Pull Changes
```bash
git pull
```

### Create and Switch Branches
```bash
# Create and switch to new branch
git checkout -b branch-name

# Switch to existing branch
git checkout branch-name

# Modern way to switch branches
git switch branch-name
```

## Advanced Git Commands

### Stashing Changes
```bash
# Stash changes
git stash

# List stashes
git stash list

# Apply latest stash
git stash pop

# Apply specific stash
git stash apply stash@{n}
```

### Merging
```bash
# Merge branch into current branch
git merge branch-name

# Abort merge in case of conflicts
git merge --abort
```

### Reset Commands
```bash
# Soft reset (keeps changes in staging)
git reset --soft HEAD~1

# Hard reset (discards changes)
git reset --hard HEAD~1

# Reset single file
git checkout -- filename
```

### View and Create Tags
```bash
# List tags
git tag

# Create tag
git tag -a v1.0 -m "Version 1.0"

# Push tags
git push --tags
```

### Resolve Merge Conflicts
When conflicts occur, edit the files manually then:
```bash
git add .
git commit -m "Resolved merge conflicts"
```

### Clean Working Directory
```bash
# Preview what will be deleted
git clean -n

# Delete untracked files
git clean -f

# Delete untracked files and directories
git clean -fd
```

## Common Git Workflows

### Feature Branch Workflow
```bash
# Create feature branch
git checkout -b feature/new-feature

# Make changes and commit
git add .
git commit -m "Add new feature"

# Push feature branch
git push -u origin feature/new-feature

# Merge back to main
git checkout main
git pull
git merge feature/new-feature
git push
```

### Updating Fork from Original Repository
```bash
# Add upstream remote
git remote add upstream https://github.com/original-owner/original-repository.git

# Fetch upstream changes
git fetch upstream

# Merge upstream changes
git merge upstream/main
```

Remember to replace `username`, `repository`, and other placeholder values with your actual information when using these commands.