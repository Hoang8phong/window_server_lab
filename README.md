# Window Server 2019 Domain Lab (Self-Directed Project)

This is a homelab project simulating a small enterorise IT environment using Window Server 2019, Window 10, and Window 11. The goal is to gain hands-on experience with Active Directory, DNS, domain management, and Group Policy.
---

## Setup Step

### 1.Configure VirtualBox Networking
- Both Vms use **Host-Only Adapter** on Adapter 1 and **NAT** on Adapter 2

### 2. Install Os
- Install **Window Server 2019** and rename to `DC01`
- Install **Window 10 Pro** and rename to `Client01`
- Install **Window 11 Pro** and rename to `Client02`

### 3. Set Static IP addresses
**DC01 (Server):**
- IP: `192.168.56.10`
- Subnet: `255.255.255.0`
- DNS: `192.168.56.10` (self)

**Client01:**
- IP: `192.168.56.11`
- Subnet: `255.255.255.0`
- DNS: `192.168.56.10` (point to server)

**Client02:**
- IP: `192.168.56.12`
- Subnet: `255.255.255.0`
- DNS: `192.168.56.10` (point to server)

### 4. Install AD DS on DC01
- Open **Server Manager** > Add Roles and Features
- Install `Active Directory Domain Services`
- Promote this server to a domain controller:
  - New forest domain: `lab.local`
  - DSRM password: set securely

### 5. Join CLient01 and Client02 to Domain
*For both machine*
- Go to: System > Rename this PC > Change
- Change workgroup to domain and set to: `lab.local`
- Enter domain admin credentials
- Reboot after successful join

### 6. Create AD User
- On DC01, open `Active Directory Users and Computers`
- Create user:
    *Client01*
    - Name: `test user`
    - Username: `testuser`
    - Password: `123@Abcd`
    - Set: "Users must change password at new logon"

      *Client02*
    - Name: `Vu Thanh Phong Hoang`
    - Username: `vuhoang`
    - Password: `123@Abcd`
    - Set: "Users must change password at new logon"
  
### 7. Log in from Client01 and Client02
- On login screen choose "Other user"
- Enter credentials above for both machine
---

## Lab Result

- Client01 and Client02 successfully joined `lab.local` domain
- AD user can log in from their machine
- However, DC01 machine cannot ping Client01 (192.168.56.11) and Client02 (192.168.56.12) machine --> maybe be blocked by firewall
    - Turn off firewall temporarily from both machine --> DC01 can ping to those machine
    - Open advanced setting --> Inbound Rules --> enable File and Printer Sharing (Echo Request - ICMPv4-In)
    - Can ping from DC01 to Client01 and Client02
---

## Task Completed

- Installed and configured Windows Server 2019
- Promoted server to Doamin Controller
- Installed and Configured DNS Server
- Joined Windows 10 Pro and Window 11 Pro to domain
- Verified connectivity and domain login
- Applied basic Group Policy Object (GPO) to restrict user access
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
- Windows 11 ISO (https://www.microsoft.com/en-us/software-download/windows11)
- Active Directory Users and Computers (AUDC)
- Group Policy Management Console (GPMC)

## Screenshort
- In screenshort file
