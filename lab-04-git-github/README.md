# Lab 04 — Version Control with Git & GitHub

## Overview
Implemented a full Git/GitHub version control workflow from scratch inside a Kali Linux VM — covering repository initialization, local commits, remote authentication, and cross-platform scripting across Linux and Windows environments.

## Tools Used
- Git (CLI)
- GitHub (reynaldovasquez50-droid)
- Kali Linux terminal (Zsh)
- Windows PowerShell
- Personal Access Token (PAT) for GitHub authentication

## What I Did

### GitHub Account & Remote Repository Setup
Created GitHub account: reynaldovasquez50-droid
Created private remote repository: my-profile
Configured local Git identity:
git config --global user.name "reynaldovasquez50-droid"
git config --global user.email "reynaldovasquez50@gmail.com"
git config --global --list

### Local Repository Initialization & First Commit
mkdir my-profile
cd my-profile
echo "strive not to be a success, but rather to be of value. -Albert Einstein" > README.md
git init
git add README.md
git commit -m "initial commit with quote"

### Pushing to GitHub
git remote add origin https://github.com/reynaldovasquez50-droid/my-profile.git
git branch -M main
git push -u origin main

Used a Personal Access Token (PAT) for secure HTTPS authentication.

### Cross-Environment Verification
- GitHub.com: README displayed correctly in browser
- Windows Host: README visible in File Explorer
- Kali Linux Guest: confirmed with ls and git log in terminal

### Shell Scripting Cross-Platform
Bash script in Kali Linux:
chmod +x hello.sh
./hello.sh

PowerShell script on Windows host:
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
./hello.ps1

## Key Takeaways
- Git tracks changes locally; GitHub hosts them remotely — separate but connected
- PATs are the current secure standard for GitHub CLI authentication over HTTPS
- The same repo is accessible across GUI and CLI environments simultaneously
- Windows execution policy must be bypassed to run unsigned local PowerShell scripts
- git config --global settings persist across all repos on the machine=
