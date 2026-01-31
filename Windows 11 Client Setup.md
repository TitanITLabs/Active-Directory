##Windows11 Client Setup##

##Virtual Machine Configuration##
Here are the following specifications for the Windows Client

Wins11 Client1
OS: Windows 11 Pro
- Windows 11 Pro is required to join an Active Directory domain.
- Supports Remote Desktop (RDP) for remote administration and testing.
- Enables full disk encryption (BitLocker) to practice endpoint security concepts.

RAM: 4 GB
- 4 GB is the recommended minimum for Windows 11.
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
  

