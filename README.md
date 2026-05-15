# Hybrid Microsoft Entra & Active Directory Lab

## Project Overview

This project expands my existing Active Directory homelab into a hybrid identity environment by integrating on-premises Active Directory with Microsoft Entra ID using Microsoft Entra Connect Sync.

The purpose of this lab is to better understand how modern organizations synchronize local domain identities with Microsoft 365 cloud services in enterprise and education environments.

This lab simulates a hybrid infrastructure commonly used in:
- School districts
- Colleges and universities
- Enterprise environments
- Managed service providers (MSPs)

---

# Objectives

- Integrate on-premises Active Directory with Microsoft Entra ID
- Learn hybrid identity concepts
- Synchronize local AD users to Microsoft Entra
- Understand cloud vs on-prem identity management
- Gain hands-on experience with Microsoft Entra Connect Sync
- Simulate enterprise authentication workflows

---

# Environment

## Virtualization Platform
- Proxmox VE

## Servers & Systems
- Windows Server 2022
- Windows 10/11 Client VM
- Microsoft Entra ID Tenant
- Microsoft Entra Connect Sync

## Domain Information
- Domain Controller: `JS3homelab`
- Local AD Domain: `JS3homelab.local`

---

# Technologies Used

- Microsoft Entra ID
- Microsoft Entra Connect Sync
- Active Directory Domain Services (AD DS)
- Windows Server 2022
- Microsoft 365 Concepts
- PowerShell
- Proxmox Virtualization

---

# Active Directory Structure

## Organizational Units (OUs)

```text
JS3homelab.local
│
├── Faculty
├── Students
├── IT_Admins
└── Test_Devices
```

## Example Users

### Faculty
- `jsalas.faculty`
- `shinojosa.faculty`

### Students
- `student1`
- `student2`

### Service Accounts
- `svc_osticket`

---

# Deployment Process

## 1. Prepared Active Directory Environment

- Verified DNS and domain functionality
- Confirmed Windows client VM could authenticate to domain
- Created Organizational Units for administrative separation
- Created test users for synchronization testing

---

## 2. Created Microsoft Entra Tenant

- Created Microsoft Entra tenant through Microsoft Developer environment
- Accessed Microsoft Entra Admin Center
- Explored tenant configuration and user management

---

## 3. Installed Microsoft Entra Connect Sync

Installed Microsoft Entra Connect Sync on the Windows Server 2022 Domain Controller to establish synchronization between local Active Directory and Microsoft Entra ID.

---

## 4. Connected Microsoft Entra ID

Authenticated using a Microsoft Entra organizational administrator account and configured synchronization between cloud and on-premises identity infrastructure.

---

## 5. Connected Active Directory Domain Services

Authenticated using local Active Directory domain administrator credentials:

```text
JS3homelab\Administrator
```

---

## 6. Configured Hybrid Identity Synchronization

Configured synchronization between:
- Local Active Directory
- Microsoft Entra ID

Synchronization completed successfully and users began appearing inside Microsoft Entra Admin Center.

---

# Verification

Successfully verified:
- Local AD users synchronized to Microsoft Entra ID
- Organizational Units synchronized correctly
- Hybrid identity environment operational
- On-premises synchronized users visible inside Entra Admin Center

---

# Synced Users

Successfully synchronized:
- `student1`
- `student2`
- `jsalas.faculty`
- `shinojosa.faculty`
- `svc_osticket`
- `testuser1`

---

# Key Concepts Learned

## Hybrid Identity

Learned how organizations integrate:
- On-premises Active Directory
- Microsoft Entra ID
- Microsoft 365 cloud identity services

---

## Password Hash Synchronization

Learned how user credentials can synchronize from local Active Directory into Microsoft cloud identity infrastructure.

---

## Tenant Management

Learned the difference between:
- Consumer Microsoft accounts (`@outlook.com`)
- Organizational Microsoft Entra accounts (`@tenant.onmicrosoft.com`)

---

## Synchronization Services

Learned how Microsoft Entra Connect Sync:
- Imports AD objects
- Synchronizes identities
- Exports identities to Microsoft Entra ID

---

# Challenges Encountered

## Incorrect Tenant Selection

Initially troubleshooting synchronization visibility due to viewing the wrong Microsoft Entra tenant directory.

Resolved by switching to the correct tenant inside Microsoft Entra Admin Center.

---

## Consumer vs Organizational Accounts

Encountered authentication issues when attempting to use a personal Outlook account instead of a Microsoft Entra organizational administrator account.

Learned the distinction between:
- Consumer Microsoft identities
- Organizational tenant identities

---

## `.local` Domain Warning

Encountered UPN suffix warnings because the homelab uses:

```text
JS3homelab.local
```

instead of a publicly routable domain.

Learned how hybrid environments typically use verified public domains in production environments.

---

# Future Expansion

Planned future scenarios include:
- Password synchronization testing
- Account disable synchronization
- Manual synchronization via PowerShell
- Microsoft 365 sign-in testing
- Microsoft Teams integration
- Microsoft Intune device management
- MFA configuration testing

---

# Resume Relevance

This project demonstrates hands-on experience with:
- Hybrid identity infrastructure
- Microsoft Entra ID
- Active Directory synchronization
- Microsoft Entra Connect Sync
- Enterprise identity concepts
- Microsoft 365 administration fundamentals
- Identity troubleshooting workflows

---
