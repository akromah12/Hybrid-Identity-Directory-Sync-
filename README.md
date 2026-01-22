# Azure Hybrid Identity Project (Windows Server 2025)

##  Project Overview
This project demonstrates the implementation of a **Hybrid Identity Infrastructure**, bridging an on-premises Active Directory environment with **Microsoft Entra ID (formerly Azure AD)**. I architected a functional lab in Microsoft Azure to simulate a corporate environment transition to the cloud.



## Technical Stack
* **Cloud Provider:** Microsoft Azure
* **Operating System:** Windows Server 2025 Datacenter (Desktop Experience)
* **Identity Services:** Active Directory Domain Services (AD DS)
* **Sync Engine:** Microsoft Entra Connect
* **Automation:** PowerShell

## Implementation Steps

### 1. Azure Infrastructure & Networking
* Provisioned a **Standard_D4s_v3** virtual machine in the **North Central US** region.
* Configured a **Static Private IP** address to ensure identity service stability.
* Established a Virtual Network (VNet) and Network Security Group (NSG) to secure RDP access.

### 2. Active Directory Domain Services (AD DS)
* Promoted the server to a **Domain Controller** for the root forest `corp.local`.
* Configured DNS and Global Catalog roles.
* Created a custom Organizational Unit (OU) named `LabUsers`.

### 3. Identity Automation (PowerShell)
* Developed and executed a PowerShell script to bulk-provision 10 users with specific attributes (Department, UPN, Password).
* **Skill Demonstrated:** Automation of redundant administrative tasks.

### 4. Entra Connect Configuration
* Installed and configured **Microsoft Entra Connect**.
* Implemented **Password Hash Synchronization (PHS)** to enable Single Sign-On (SSO).
* Resolved UPN suffix matching issues to ensure cloud synchronization success.

## 📊 Verification & Results
* **On-Premises:** Verified user objects in *Active Directory Users and Computers*.
* **Sync Engine:** Confirmed "Success" status in the *Synchronization Service Manager*.
* **Cloud:** Verified that all users appeared in the *Microsoft 365 Admin Center* with the status "Synced from on-premises."



## 💡 Key Challenges & Solutions
* **Quota Restrictions:** Initially encountered vCPU limits in East US. Resolved by pivoting to North Central US and selecting a high-performance D-series instance to ensure a smooth Windows Server 2025 GUI experience.
