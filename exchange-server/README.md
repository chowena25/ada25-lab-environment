# Exchange Server 2019 CU14 – Mailbox Role Setup

This server hosts the Exchange Server 2019 Mailbox role for the ADA25 on-prem Active Directory lab.  
It is used for learning mail transport, mailbox databases, certificate configuration, and hybrid readiness.

---

## 🖥️ Server Details
- Windows Server 2022
- Exchange Server 2019 CU14 (Mailbox role)
- Joined to domain: **ADA25.local**
- Installed after schema and AD preparation
- RAM increased to support installation
- Disk space extended after running low during setup

---

## 📦 Prerequisites Installed
Before Exchange installation, the following prerequisites were installed:

- Unified Communications Managed API (UCMA) 4.0 Runtime  
- Visual C++ 2013 Redistributable (x64)  
- IIS URL Rewrite Module  
- .NET Framework components  
- Server roles & features added using PowerShell:
Install-WindowsFeature Server-Media-Foundation, RSAT-ADDS, Web-WebServer, Web-Metabase, Web-Asp-Net45, Web-ISAPI-Ext, Web-Mgmt-Console, WAS-Process-Model, NET-HTTP-Activation, NET-Non-HTTP-Activations
---

## 🏗️ Exchange Installation Steps

### 1. AD Schema Preparation
Ran:
Setup.exe /PrepareSchema /IAcceptExchangeServerLicenseTerms_DiagnosticDataOFF
Setup.exe /PrepareSchema /IAcceptExchangeServerLicenseTerms_DiagnosticDataOFF
- Completed without errors  
- Schema version verified using ADSI Edit  

### 2. AD Preparation
Setup.exe /PrepareAD /IAcceptExchangeServerLicenseTerms_DiagnosticDataOFF
### 3. Exchange Server Installation
- Launched setup in GUI
- Selected **Mailbox role**
- Pointed to correct installation path
- Installation completed after fixing RAM/disk issues
- Services verified in Services.msc

---

## 🛠️ Troubleshooting Performed

### ❌ Setup stuck during installation  
Reason: low RAM and limited disk space  
Fix:
- Increased VM RAM using Hyper-V Dynamic Memory  
- Expanded C: drive  
- Re-ran setup successfully

### ❌ ECP/OWA inaccessible  
Fix:
- Ensured IIS was fully installed  
- Restarted MSExchange services  
- Verified DNS A records

### ❌ SharePoint installation blocking Exchange  
Fix: sequenced installation properly after increasing RAM and storage

---

## 📬 Post-Installation Validation

- Logged into **ECP**:  
  https://ada25-dc1/ecp  
- Logged into **OWA**:  
  https://ada25-dc1/owa  

- Verified:
  - Mailbox database mounted  
  - Exchange services running  
  - PowerShell access via Exchange Management Shell  

---

## 🎯 Outcome
Exchange Server 2019 CU14 is fully installed and functional, supporting:
- Mailbox creation  
- Mail flow testing  
- ECP/OWA administration  
- Lab-ready hybrid/modern auth learning  

This server plays a major role in demonstrating enterprise-level IT support and admin capability.
