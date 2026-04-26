# Lab 02 — CLI Environments & Shell Scripting

## Overview
Practiced essential command-line operations in both Bash and PowerShell within Visual Studio Code, covering directory navigation, file creation, and basic shell scripting across two different OS environments.

## Tools Used
- Visual Studio Code (integrated terminal)
- Git Bash (Unix-style shell on Windows)
- PowerShell
- Windows File Explorer (GUI comparison)

## What I Did

### Environment Setup
Configured VS Code to run both PowerShell and Git Bash terminals simultaneously:
whoami
date

### Directory Navigation & File Creation (Bash)
mkdir IS-1003
cd IS-1003
mkdir lab_test
cd lab_test
touch example.txt
ls

### Cross-Shell File Verification (PowerShell)
Navigated to the same directory in PowerShell and confirmed the file created in Bash was accessible:
cd IS-1003
cd lab_test
dir

### GUI vs CLI Comparison
Viewed the same lab_test directory in both Windows File Explorer and PowerShell terminal side by side.
- GUI (File Explorer): icons, file type, date modified — easy visual navigation
- CLI (PowerShell): file permissions, exact timestamps, file size — precise technical detail

### Shell Scripting
Bash script (hello.sh):
echo "Hello!" > hello.sh
chmod +x hello.sh
./hello.sh

PowerShell script (hello.ps1):
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\hello.ps1

## Key Takeaways
- Bash requires chmod +x to grant execution permissions before running scripts
- PowerShell requires execution policy adjustment to run local unsigned scripts
- Both shells share the same underlying filesystem
- CLI provides more precise file metadata than GUI views=
