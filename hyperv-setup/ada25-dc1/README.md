# ADA25-DC1 – Windows Server 2022 Domain Controller

This VM is the core of the ADA25 on-prem Active Directory lab.  
It provides Active Directory Domain Services, DNS, and management tools for the entire lab environment.

---

## 🖥️ Server Details
- Windows Server 2022 Standard (Evaluation)
- VM Name: **ADA25-DC1**
- Domain: **ada25.local**
- IPv4 Static Address: 192.168.x.x (Internal Lab Network)
- RAM: Dynamic Memory (~11 GB)
- HDD: 60–80 GB

---

## 🚀 Configuration Steps Completed

### **1. Installed and configured Active Directory Domain Services (AD DS)**
- Promoted server to Domain Controller
- Created new forest: **ada25.local**
- Installed DNS automatically during AD DS installation
- Verified replication, SYSVOL, and NETLOGON shares

### **2. OU Structure Created**
- `ADA25 Users`
- `ADA25 Computers`
- Sub-OUs for testing:  
  - `Staff`  
  - `IT`  
  - `Test Machines`

### **3. Group Policy Objects (GPOs)**
- Wallpaper GPO created and applied
- Wallpaper stored in:
