# Windows Server 2022 Setup Guide

## Overview

This guide provides step-by-step instructions to set up **Windows Server 2022** for an Active Directory home lab. It is intended for learning and practicing enterprise IT tasks in a safe, virtual environment.

---

## Step 1: Installation

   1. Open your virtualization software.
   2. Created a new VM with the following specs:
   6GBs of Ram
   2 CPU cores
   40GB Virtual Hard Drive Space (Installed on NVME for faster performance)
   3. Mounted the Windows Server ISO
   4. Selected Datacenter Evaluation (Desktop Experience) **Chosen for the GUI**
![Version Selection](https://github.com/TitanITLabs/Active-Directory/blob/b3c6f12f069306c7b19a5e6f399744b5ad723e30/Images/VersionSelection.png)

---
## 🌐 Network Setup

![Network Setup](Images/NAT.png)

*Figure 1: NAT adapter configuration.*  
The **NAT adapter** is used to provide the virtual machine with internet connectivity through the host machine (your home router). This allows the server to access updates, download tools, and communicate with external networks.

![Network Setup](https://github.com/TitanITLabs/Active-Directory/blob/2cea6719512f4d855357fad97732e5c5fb6d3fff/Images/Internal.png)

*Figure 2: Internal adapter configuration.*  
The **Internal adapter** is used for the lab network, allowing the virtual machine to communicate with other lab VMs (like domain-joined clients) without exposing them directly to the internet. The domain controller handles internal network connectivity and routing between VMs.

