** DNS Troubleshooting **

During the creation of the lab I made a mistake causing the Client to not be able to access the internal network, as well as not being able to connect to the domain

My first thought was well I'm not getting any internet connectibity so obviously I went to network connections to see if it was properly getting an IP from the DHCP server

![NoConnectivity](https://github.com/TitanITLabs/Active-Directory/blob/c9249aa365851f2f58e64bd1955d700e0552bd57/Images/NoConnectivity.png)

![NetworkSettings](https://github.com/TitanITLabs/Active-Directory/blob/282fb46164ef80ee0c791d7156edd576d45add5f/Images/NetworkSettings.png)

It was set to automatic, and I also did an IPConfig to see if I was getting an APIPA Address I was not I was getting a address from the scope meaning DHCP was not the problem
I then proceeded to try and join the domain which it could not find prompting me to go do an nslookup of my domain

![NSLookup]()

As shown the gateway internal network existed since the default gateway was there, but I noticed that the ip it was getting was an IP it was getting from the internet connection going out to the actual public internet
This gave me a starting point on what to research so I researched how come my domain exists, but it cannot connect properly.
I found an answer saying that if it using a public DNS server  cannot access the internal resources in terms not allowing an IP to be grabbed due to it being tied to the internal resources

I went through my set up for DHCP and DNS to find this behemot looking straight at my face.

![IncorrectDNSSetup]()

Once I removed it from the list entirely (setting it as secondary also works) I was able to get the proper internet connection

![Connectivity]()
