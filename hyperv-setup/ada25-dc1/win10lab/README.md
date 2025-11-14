# Win10Lab – Windows 10 Client (Domain Joined)

This VM is used for testing Group Policies, domain join operations, RSAT tools, authentication, and client-side troubleshooting within the ADA25 on-prem Active Directory lab.

---

## 🖥️ VM Details
- Windows 10 Pro (Evaluation)
- VM Name: **Win10Lab**
- Connected to internal lab switch
- Dynamic Memory enabled
- Installed Hyper-V guest services for clipboard/keyboard/mouse integration

---

## 🔗 Domain Join Process

### **1. Network Preparation**
- Verified VM receives IP from internal virtual switch  
- Confirmed DNS server = ADA25-DC1 IP  
- Tested with:

### **2. Joining the Domain**
- Joined domain **ADA25.local**
- Rebooted and logged in as:  
or your domain user account.

### **3. Fixes During Domain Join**
- VM originally failed to start due to **missing VHD/ISO path**
- Repaired by re-attaching disk via Hyper-V settings  
- Enabled “Automatic Start Action” with delay to avoid RAM conflict  
- Fixed enhanced session connection for keyboard/mouse

---

## 🛠️ RSAT Installation (Remote Server Administration Tools)

Installed RSAT to manage Active Directory directly from the Win10 client:

Run:

Tools verified:
- AD Users & Computers
- DNS Manager
- Group Policy Management Console (GPMC)

---

## 🖼️ GPO Wallpaper Testing

This VM was used to test and validate Group Policy Objects from DC1.

### **1. Steps Performed**
- Verified SYSVOL path accessible:
