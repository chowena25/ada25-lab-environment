# SharePoint Subscription Edition – Application Server

This VM hosts SharePoint Subscription Edition (SE) used for enterprise collaboration testing within the ADA25 on-prem lab.

It integrates with Active Directory, SQL Server 2019 (built-in), and Exchange Server to simulate a full enterprise environment.

---

## 🖥️ Server Details

- Windows Server 2022  
- SharePoint Subscription Edition (latest ISO)  
- Domain joined: **ada25.local**  
- RAM increased after initial failures  
- C: drive expanded due to setup crashes  
- SQL Server installed automatically as part of SharePoint SE prerequisites  

---

## ⚙️ Prerequisites Installed

SharePoint SE required several prep components:

- .NET Framework  
- IIS + Application Development features  
- Windows Server Roles:  
  - Web-Server  
  - Web-WebServer  
  - Web-Asp-Net45  
  - Web-Mgmt-Console  
  - WAS  
  - NET-WCF-HTTP-Activation  
- SQL Native Client + SQL Management features  
- Visual C++ Redistributables  
- SharePoint SE Prerequisite Installer (prereq.exe)

All prerequisites completed successfully after expanding RAM & storage.

---

## 🚀 Installation Steps Completed

### **1. Ran SharePoint SE Setup**
- Mounted ISO  
- Entered product key  
- Chose “Single-Server Farm”  
- Selected installation directory  
- Downloaded missing components  
- Rebooted VM when prompted  

### **2. Configuration Wizard (psconfigui.exe)**
- Created new SharePoint configuration database  
- Connected to local SQL instance  
- Created SharePoint Central Administration site  
- Started required SharePoint services  

### **3. Verified Successful Farm Creation**
- SharePoint Management Shell functional  
- Central Administration accessible  
  - http://ada25-dc1:8812/  
- Verified farm configuration using PowerShell:  

---

## ❌ Issues Encountered & Fixes

### **1. Setup freezing / black screen**
**Reason:** VM left running overnight without reboot + low RAM  
**Fix:**  
- Increased VM RAM  
- Restarted Hyper-V host + VM  

---

### **2. psconfigui.exe failing**
**Reason:** Not enough RAM + missing prerequisites  
**Fix:**  
- Installed all prerequisites  
- Expanded disk space  
- Re-ran configuration wizard successfully  

---

### **3. Setup crashing when browser closed**
SharePoint Setup uses a browser-based configuration (Edge).  
Closing Edge stops the process.

**Fix:**  
- Kept Edge open until installation completed  
- Avoided switching VMs during setup  

---

## 🧪 Post-Installation Validation

Verified:

- Central Administration loads correctly  
- SharePoint farm ID created  
- All core services running  
- SQL instance connected  
- SharePoint Management Shell available  
- Able to create new web applications/site collections  

---

## ✅ Outcome

SharePoint Subscription Edition is fully installed and functional, supporting:

- Enterprise collaboration testing  
- Modern SharePoint admin tools  
- Integration with Active Directory  
- Integration with Exchange Server  
- PowerShell automation via SharePoint Management Shell  

This VM demonstrates your ability to deploy **large, real enterprise systems** end-to-end, including repair of installation failures, RAM/disk tuning, and prerequisite validation.
