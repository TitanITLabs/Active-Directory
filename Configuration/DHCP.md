# Configuration Steps

- Use Server Manager to install DHCP
  - Open **Add Roles and Features**
  - Select **DHCP Server**
  - Complete the setup wizard


  ![InsatllationDHCP](https://github.com/TitanITLabs/Active-Directory/blob/c4cf4c33bcf62c556e6a9b52be0ddef2a64d5810/Images/DHCPServerRoles.png)

  # DHCP Setup!!

  Following steps to configure DHCP

- Within the DHCP console:
  - Right-click **IPv4** and select **New Scope**
  - Enter the following configuration:
    - **Scope Name** (use a descriptive name; avoid using the IP range as the name)
    - **Optional description**
    - **IP address range:** `172.16.0.100 – 172.16.0.200`
    - **Subnet mask:** `255.255.255.0 (/24)`
    - **Lease duration** (as appropriate for the environment)
    - **Default gateway:** internal gateway IP
    - **Exclusions** (optional, for printers or devices requiring static IPs)
    - **DNS server:** `172.16.0.1` (Domain Controller)
      - Ensure the internal DNS server is set as **primary** to maintain domain and internet connectivity


  ![IPRange](https://github.com/TitanITLabs/Active-Directory/blob/78ff4bbe7b2ebf8978e2b24e04c58b78990afcdd/Images/Scope.png)

  ![Duration](https://github.com/TitanITLabs/Active-Directory/blob/33ea93725e83dfa586ad08c66b5de688a5a63efb/Images/Duration.png)

  ![Exclusions](https://github.com/TitanITLabs/Active-Directory/blob/56fd84a4c044a6c0a9e72100fe9fe9d987ddaeed/Images/Exclusion.png)

  ![DefaultGateway](https://github.com/TitanITLabs/Active-Directory/blob/223efa61d2b0f0ee36c210f602a67d7a6d2e8243/Images/DefaultGateway.png)

  ![DNS]()

  
