# Window Server 2019 Domain Lab (Self-Directed Project)

This is a homelab project simulating a small enterorise IT environment using Window Server 2019 and Window 10. The goal is to gain hands-on experience with Active Directory, DNS, domain management, and Group Policy.
---

## Lap Setup

### Machines Used
- **DC01**: Window Server 2019 (Standard Desktop Experience)
  - Roles indtalled: Active Directory Doamin Services, DNS Server
  - Domain: lab.local
  - IP Address: 192.168.56.10
    
- **Client01**: Window 10 Pro
  - IP Address: 192.168.56.11
  - Joined to domain lab.local

### VirtualBox Network
- **Host-only Adapter** (vboxnet0) for isolated internal communication
---

## Task Completed
- Installed and configured Windows Server 2019
- Promoted server to Doamin Controller
- Installed and Configured DNS Server
- Joined Windows 10 Pro to domain
- Verified connectivity and domain login
- Applied basic Group Policy Object (GPO) to restrict user access
---

## Screenshots
![Active Directory Users and Computers](https://github.com/user-attachments/assets/669abfc3-d51e-430d-9d9c-3326f093e58d)


![Server Manager](https://github.com/user-attachments/assets/dcf02106-3a61-46ef-8fd5-81fba297c925)


![Command Prompt ping 192 168 56 10  in Client01 machine](https://github.com/user-attachments/assets/3eb51071-781e-49fa-b074-10e02ced2d8a)


![System Properties of Client01 machine](https://github.com/user-attachments/assets/c6e9699a-b456-4ae5-9235-b85564897746)


![testuser login screen](https://github.com/user-attachments/assets/ff474996-fea1-462e-978d-b63412cdf72c)


![testuser account of Client01 machine](https://github.com/user-attachments/assets/a8a0619d-23b9-46e7-a9de-32ecff29cc30)


![Groip Policy Management console](https://github.com/user-attachments/assets/16810d9f-69dd-4410-805e-761ee6dc2b3c)
---

## What I learned

- Hand-on configuration of Active Directory Domain Server
- Network communication between domain controller and clients
- DNS resolution in internal domain environments
- Applying and troubleshooting Group Policies
- Simulating enterprise IT support scenatios in a safe lab
---

## Tools Used
- Oracle VirtualBox (https://www.virtualbox.org/wiki/Downloads)
- Windows Server 2019 ISO (Evaluation) (https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2019)
- Windows 10 ISO (https://www.microsoft.com/en-au/software-download/windows10iso)
- Active Directory Users and Computers (AUDC)
- Group Policy Management Console (GPMC)  
