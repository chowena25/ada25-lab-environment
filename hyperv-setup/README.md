# Hyper-V Host Setup (Windows 11 Pro)

This section documents how I prepared my local machine to run an enterprise-grade on-premises lab using Hyper-V.

## 🖥️ Host Machine Specs
- Windows 11 Pro
- Intel Core i7-1260P
- 48 GB RAM
- 1 TB SSD
- Hyper-V enabled via Windows Features

## ⚙️ Tasks Completed
- Enabled Hyper-V and all sub-components
- Fixed Hyper-V admin permissions (added `maths` account to Hyper-V Administrators group)
- Created Virtual Switch for internal lab network
- Tuned VM RAM settings (Dynamic Memory ~11 GB for DC1)
- Resolved VM boot issues caused by missing/corrupted VHD/ISO path
- Fixed screen/keyboard integration settings for VMs

## 🔧 Outcome
Hyper-V host fully prepared to run:
- ADA25-DC1 (Server 2022 Domain Controller)
- Win10Lab client
- SharePoint Subscription Edition server
- Exchange Server 2019 CU14 server
