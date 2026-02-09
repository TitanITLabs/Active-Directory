# DNS Misconfiguration Preventing Domain Connectivity 

## Issue Overview

During the creation of this lab, a DNS misconfiguration caused a domain joined client to be unable to access internal domain resources or successfully join the domain, despite receiving a valid IP address.

Symptoms

-Client received a valid IP address from the DHCP scope

-No APIPA address was assigned

-Client was unable to locate or join the domain

-Internal resources could not be resolved

Initial Troubleshooting

Because the client lacked proper connectivity, the first assumption was a DHCP issue.

![NoConnectivity](https://github.com/TitanITLabs/Active-Directory/blob/c9249aa365851f2f58e64bd1955d700e0552bd57/Images/NoConnectivity.png)

![NetworkSettings](https://github.com/TitanITLabs/Active-Directory/blob/282fb46164ef80ee0c791d7156edd576d45add5f/Images/NetworkSettings.png)

Steps taken:

-Verified the network adapter was set to obtain an IP address automatically

-Ran ipconfig /all to confirm addressing

-Confirmed the client received an IP address from the correct DHCP scope

Since the client received a valid IP address and default gateway, DHCP was ruled out as the cause.

Further Investigation

When attempting to join the domain, the client was unable to locate the domain controller.
An nslookup of the domain name revealed that DNS resolution was showing the Domain Name even the default gateway. but still not able to connect


![NSLookup](https://github.com/TitanITLabs/Active-Directory/blob/7f8aff8dfce36fe3d20c8f66402c4ba8b125036d/Images/Domainnotfound.png)

Upon further research online it was learned that Domain Connection could not be possible if there is a public dns server being used as the primary

**Root Cause**

This was the exact case as The DHCP configuration mistakenly prioritized Google’s public DNS server (8.8.8.8) instead of the internal Active Directory DNS server.
Because Active Directory relies on internal DNS records for domain discovery and authentication, this prevented:

-Domain name resolution

-Domain controller location

-Access to internal network resources

![IncorrectDNSSetup](https://github.com/TitanITLabs/Active-Directory/blob/85a4f042bddf7bc007c04063776115c8a08a11a3/Images/DnsError.png)

**Resolution**

-Removed the Public DNS server from the list

-Joined Domain

-Renewed the client’s DHCP lease connectivity achieved due to access to internal resources now

![Connectivity](https://github.com/TitanITLabs/Active-Directory/blob/04e14d0cd30dfe67903f55d44ad317abb010a506/Images/ConnectivityFixed.png)
