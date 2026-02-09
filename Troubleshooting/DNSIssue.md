# DNS Misconfiguration Preventing Domain Connectivity 

## Issue Overview

During the creation of this lab, a DNS misconfiguration caused a domain joined client to be unable to access internal domain resources or successfully join the domain, despite receiving a valid IP address.

![NoConnectivity](https://github.com/TitanITLabs/Active-Directory/blob/c9249aa365851f2f58e64bd1955d700e0552bd57/Images/NoConnectivity.png)

![NetworkSettings](https://github.com/TitanITLabs/Active-Directory/blob/282fb46164ef80ee0c791d7156edd576d45add5f/Images/NetworkSettings.png)

It was set to automatic, and I also did an IPConfig to see if I was getting an APIPA Address I was not I was getting a address from the scope meaning DHCP was not the problem
I then proceeded to try and join the domain which it could not find prompting me to go do an nslookup of my domain

![NSLookup](https://github.com/TitanITLabs/Active-Directory/blob/7f8aff8dfce36fe3d20c8f66402c4ba8b125036d/Images/Domainnotfound.png)

As shown the gateway internal network existed since the default gateway was there, but I noticed that the ip it was getting was an IP it was getting from the internet connection going out to the actual public internet
This gave me a starting point on what to research so I researched how come my domain exists, but it cannot connect properly.
I found an answer saying that if it using a public DNS server  cannot access the internal resources in terms not allowing an IP to be grabbed due to it being tied to the internal resources

I went through my set up for DHCP and DNS to find this behemot looking straight at my face.

![IncorrectDNSSetup](https://github.com/TitanITLabs/Active-Directory/blob/85a4f042bddf7bc007c04063776115c8a08a11a3/Images/DnsError.png)

Once I removed it from the list entirely (setting it as secondary also works) I was able to get the proper internet connection

![Connectivity](https://github.com/TitanITLabs/Active-Directory/blob/04e14d0cd30dfe67903f55d44ad317abb010a506/Images/ConnectivityFixed.png)
