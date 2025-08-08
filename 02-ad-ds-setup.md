# Windows Server 2019 – Active Directory Domain Services (AD DS) Setup

## Overview
This post documents the installation and configuration of Active Directory Domain Services on a Windows Server 2019 VM.  
This server will act as the domain controller for my home lab, providing centralized authentication, DNS, and DHCP services.

---

## Tools Used
- VMware Workstation Player 17  
- Windows Server 2019 LTSC Enterprise ISO (downloaded from Microsoft)

---

## VM Configuration
| Setting         | Value                |
|-----------------|----------------------|
| CPUs            | 2 vCPUs              |
| Memory          | 4 GB                 |
| Disk Size       | 40 GB                |
| Network         | NAT (initially DHCP) |
| Hostname        | `WIN-SERVER-AD`      |

---

## Installation Steps
1. Installed Windows Server 2019 using the ISO in VMware.
2. Allowed the server to be discoverable by PC's on the same network. 
3. Set the hostname to `WIN-SERVER-AD`.  
4. Configured a **static IP address** for the server (e.g., 192.168.191.10).  
5. Installed the **Active Directory Domain Services** role via Server Manager.  
6. Promoted the server to a **Domain Controller**, creating a new forest and domain (e.g., `home.lab`).  
7. Configured **DNS** during the promotion wizard.  
8. Verified AD DS, DNS, and DHCP services started successfully.  
9. Created initial users and groups for the lab domain.  

---

## What I Learned
- Importance of assigning a static IP to the domain controller.  
- How DNS integrates with AD for name resolution.  
- The process of creating and managing a new AD forest.  

---

## Next Steps
- Setup DHCP server role and configure scopes for client IPs.  
- Join Windows 10 clients to the domain.  
- Configure Group Policy Objects (GPOs) for lab users.

---

## Screenshots
![Setting IP](IPv4-Settings.png)
![Initial dashboard](images/WServ-Install.png)  
![AD DS Installation](images/ADDS.png)  
![Promote to Domain Controller](images/Promote-server.png)
![Dashboard after promoting](images/Dashboard.png)  
![Verifying & creating lab admin account](images/server-users.png)

