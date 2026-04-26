# Lab 03 — Virtualization & Kali Linux Setup

## Overview
Deployed a fully functional Kali Linux virtual machine using Oracle VirtualBox on a Windows 11 host. Configured virtual hardware, resolved boot and display issues, and established a seamless host-guest workflow for future security testing.

## Tools Used
- Oracle VirtualBox 7.x
- Kali Linux 2025.4 (ISO installer)
- Windows 11 (Host OS)
- Kali Linux Xfce Desktop (Guest OS)

## Host System Specs
- CPU: AMD Ryzen 7 9800X3D (8-core, virtualization enabled)
- RAM: 32GB
- Storage: NVMe SSD
- Host OS: Windows 11

## What I Did

### VM Hardware Configuration
- Base Memory: 4096 MB RAM
- Processors: 2 vCPUs
- Video Memory: 128 MB
- Shared Clipboard: Bidirectional
- Drag-and-Drop: Bidirectional

### Installation
- Downloaded Kali Linux 2025.4 ISO and VirtualBox 7.2.6 installer
- Completed full installation including GRUB bootloader configuration
- Manually specified /dev/sda as the bootloader target
- Successfully logged in with credentials created during setup

### Troubleshooting — Display Resolution
Guest OS display would not auto-resize. Resolved via CLI:
xrandr --output Virtual-1 --auto

### Host-Guest Integration
- Installed VirtualBox Guest Additions for full display scaling
- Verified bidirectional clipboard by passing text from Windows host into Kali terminal
- Confirmed drag-and-drop functionality between host and guest

## Key Takeaways
- Virtualization creates an isolated sandbox — experiments cannot affect the host OS
- GRUB bootloader requires correct device path /dev/sda to boot properly
- xrandr is the CLI tool for managing display output when GUI settings fail
- Guest Additions are essential for smooth host-guest workflow
- VMs allocate RAM and CPU independently from the host at runtime=
