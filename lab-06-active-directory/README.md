# Lab 06 - Active Directory & Group Policy Homelab

## Overview
Built a functional Active Directory Domain Services (AD DS) environment using Windows Server 2022 in VirtualBox to simulate enterprise IT administration tasks.

## Environment
- Hypervisor: Oracle VirtualBox 7.2.6
- Server OS: Windows Server 2022 Standard Evaluation
- Domain: vasquez.local
- NetBIOS Name: VASQUEZ

## What I Did

### 1. Promoted Server to Domain Controller
- Installed AD DS role via Server Manager
- Created a new forest with root domain vasquez.local
- Configured DNS and Global Catalog on the domain controller

### 2. Created Organizational Unit (OU)
- Opened Active Directory Users and Computers
- Created OU named "IT Department" under vasquez.local
- Simulates how enterprises organize users by department

### 3. Provisioned User Account
- Created user John Smith (jsmith@vasquez.local) inside IT Department OU
- Configured password settings and account properties
- Mirrors real-world onboarding workflows in IT support roles

### 4. Configured Group Policy Object (GPO)
- Created GPO named "Password Policy" linked to vasquez.local
- Set minimum password length to 12 characters
- Enabled password complexity requirements
- Demonstrates enforcement of security baselines across domain users

## Skills Demonstrated
- Active Directory Domain Services (AD DS)
- Organizational Unit (OU) design
- User account provisioning and IAM concepts
- Group Policy Object (GPO) creation and configuration
- Windows Server 2022 administration

## Tools Used
- Oracle VirtualBox
- Windows Server 2022
- Active Directory Users and Computers (ADUC)
- Group Policy Management Console (GPMC)
==
