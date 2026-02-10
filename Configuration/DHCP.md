# Configuration Steps

- Use Server Manager to install DHCP
  - Open **Add Roles and Features**
  - Select **DHCP Server**
  - Complete the setup wizard


  ![InsatllationDHCP](https://github.com/TitanITLabs/Active-Directory/blob/c4cf4c33bcf62c556e6a9b52be0ddef2a64d5810/Images/DHCPServerRoles.png)

  # DHCP Setup!!

  Following steps to configure DHCP

  Within the console
  
  -Right click on IPV4 and click new scope
  
  -Enter the following:
  -Scope Name (Mine is the range I'm using I suggest an actual name)
    
  -Optional Description
     
  -IP Range 172.16.0.100 - 172.16.0.200
  
  -Subnet Mask 255.255.255.0/24
  
  -Set Lease Duration
    
  -Set Default Gateway to gather the IP addresses
    
  -Optional exclusions for a printer or other devices that a static IP is more suited for
     
  -DNS Server Pointed it to the domain controller's IP 172.16.0.1 (Make sure to set it as primary otherwise no internet connectivity will occur)

  ![IPRange]()

  ![Duration](https://github.com/TitanITLabs/Active-Directory/blob/33ea93725e83dfa586ad08c66b5de688a5a63efb/Images/Duration.png)

  ![Exclusions](https://github.com/TitanITLabs/Active-Directory/blob/56fd84a4c044a6c0a9e72100fe9fe9d987ddaeed/Images/Exclusion.png)

  ![DefaultGateway](https://github.com/TitanITLabs/Active-Directory/blob/223efa61d2b0f0ee36c210f602a67d7a6d2e8243/Images/DefaultGateway.png)

  ![DNS]()

  
