# Windows11 Client Setup

## Virtual Machine Configuration 
Here are the following specifications for the Windows Client

Wins11 Client1
OS: Windows 11 Pro
- Windows 11 Pro is required to join an Active Directory domain.
- Supports Remote Desktop (RDP) for remote administration and testing.
- Enables full disk encryption (BitLocker) to practice endpoint security concepts.

RAM: 4 GB
- 4 GB is the recommended amount for Windows 11.
- Sufficient for domain login, Group Policy processing, and administrative tasks without over-allocating host resources.

CPU: 3 vCPUs
- Allocated to ensure smooth performance during domain logins, Group Policy updates, and multitasking.
- Prevents performance bottlenecks when testing AD-related tasks.

Disk: 20 GB
- Minimal disk size chosen since the VM is used primarily for AD testing.
- Enough space for the OS, domain tools, updates, and log files without unnecessary storage usage.

Notes:
- Joined to the domain to test user authentication, Group Policy enforcement, and workstation management.
- Used to validate domain policies from an end-user perspective.
 ![ClientConfig](https://github.com/TitanITLabs/Active-Directory/blob/b0666761c44d3e1e075f55c6285f5de41bb6bd92/Images/ClientCpuSetup.png)
 ![ClientConfig](https://github.com/TitanITLabs/Active-Directory/blob/b0666761c44d3e1e075f55c6285f5de41bb6bd92/Images/ClientSetup.png)
  

## Network Setup 
Figure 1:

![NetworkSettings](https://github.com/TitanITLabs/Active-Directory/blob/75d6f4664ca58cf450419728867ef6ed7b2390a3/Images/NetworkSettings.png)

This image shows the client workstation connected to the internal network provided by the domain controller. It also confirms that DHCP and DNS are functioning correctly. Additional verification is shown in the following image.

Figure 2:

![IpConfig](https://github.com/TitanITLabs/Active-Directory/blob/75d6f4664ca58cf450419728867ef6ed7b2390a3/Images/IPConfig.png)

This figure shows the client workstation receiving an IP address from the 172.1.0.100–172.1.0.200 DHCP scope on the domain controller. The presence of the domain DNS suffix in the ipconfig output further confirms successful domain membership.


##Joining Domain

Steps for a client to join a domain:

- Navigate to Settings → System → About → Rename this PC (Advanced)
- Select Change and choose the Domain option
- Enter the target domain name
- Authenticate using domain administrator credentials
- Restart the system to apply the changes

Figure 3:

![DomainJoined](https://github.com/TitanITLabs/Active-Directory/blob/2610a69a55b6fd5846cc57077cd9860326cb9bed/Images/DomainJoin.png)

## Verification Of Joined Domain

Figure 4:

Used systeminfo | findstr Domain &
ipconfig /all for further confirmation of the client joining the domain
![DomainProof](https://github.com/TitanITLabs/Active-Directory/blob/8243f993ed779bf69e9cad7dbb3bd1665a0b0076/Images/DomainProof.png)
