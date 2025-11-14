# Microsoft 365 Hybrid Integration – ADA25 Lab

This section documents the hybrid connectivity and identity integration between the on-prem ADA25 Active Directory environment and Microsoft 365 Developer tenant.

The goal of this hybrid setup is to simulate real enterprise identity, syncing, and cloud-service management scenarios.

---

## 🌐 Hybrid Identity Overview

The hybrid identity model used in this lab includes:

- On-prem Active Directory Domain Services (ADA25-DC1)
- Entra ID (formerly Azure AD) from Microsoft 365 Developer Program
- Azure AD Connect (Sync Engine)
- Hybrid Join (Devices registered & joined to both AD DS + Entra)
- Password Hash Sync (PHS)
- Seamless SSO (SSO token from on-prem AD)

This replicates what most UK organisations use today in production.

---

## 🖥️ On-Prem Requirements

- Active Directory Domain Controller  
  **ADA25-DC1 (Windows Server 2022)**  
- DNS correctly resolving internal hostnames
- Outbound access to Microsoft endpoints
- Win10Lab client domain-joined to **ada25.local**
- Correct UPN suffix configured:

UPN suffix added in:
**Active Directory Domains and Trusts → Properties**.

---

## 🔧 Azure AD Connect Installation & Setup

Installed on **ADA25-DC1**:

### 1. Downloaded Azure AD Connect from Microsoft
Version: Latest cloud-supported build

### 2. Configured Sync Options
Enabled:

- Password Hash Sync (PHS)
- Seamless Single Sign-On
- Hybrid Azure AD Join (Windows 10/11)

### 4. Synced Selected OUs
Synced OUs:

- ADA25 Users
- ADA25 Computers
- Test Machines

Verified first sync using:

Confirmed cloud objects in:
**Entra Admin Center → Users → Devices → Groups**

---

## 🖥️ Device Hybrid Join (Win10Lab)

Win10Lab was hybrid-joined automatically after sync.

### Validated using:

**CMD:**


### 3. Connected to Microsoft 365 Developer Tenant
Logged in with:

Confirmed:

- AzureAdJoined = YES  
- DomainJoined = YES  
- SSO = YES  
- WorkplaceJoined = YES  

This proves the device is successfully hybrid joined.

---

## 🔐 SSO Validation

From Win10Lab:

Tested access to Microsoft 365 apps:

- Outlook Web  
- SharePoint Online  
- Teams  
- Admin Center (limited access)

SSO worked using domain credentials:
without re-entering the password.

---

## ☁️ Cloud Services Integration

### Exchange Online
- Validated mailbox provisioning
- Logged into Outlook Web App (OWA)
- Tested mail flow between:
  - On-prem Exchange 2019 (Mailbox role)
  - Exchange Online mailbox

### SharePoint Online
- Accessed through hybrid device
- Verified SSO with SharePoint Online sites
- Confirmed Azure AD token issuance

---

## 🔎 Troubleshooting Performed

### ❌ Issue: Device not hybrid joining
Fix:
- Checked `AzureAD Connect > Device Sync`
- Forced sync
- Restarted Win10Lab
- Ensured correct UPN suffix

### ❌ Issue: SSO not working
Fix:
- Ensured Seamless SSO enabled
- Validated Kerberos decryption key
- Reset computer account in On-Prem AD

### ❌ Issue: Objects not syncing
Fix:
- Repair tool inside Azure AD Connect
- Checked OU filtering
- Cleared duplicate UPNs

---

## ✅ Outcome

The ADA25 Lab now supports full hybrid operation:

- On-prem AD synced to Microsoft 365  
- Hybrid Azure AD join for Win10 clients  
- Password Hash Sync + Seamless SSO  
- Test users sign into Microsoft 365 using **on-prem AD credentials**  
- Mail flow tested between Exchange On-Prem & Exchange Online  
- SharePoint Online accessible via SSO  

This hybrid environment accurately simulates a **real enterprise Microsoft ecosystem** used by IT Support, System Administrators, and Cloud Engineers.

---

