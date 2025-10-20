## 🛡️ **Security & Encryption**

Tasks related to certificates, SSH, and secure connections.

1. **(12)** Create a CSR request to retrieve a certificate from an external provider.
- cum fac bani cei de la forma de csr? daca e gatis? cel putine cele care sunt gratis
- deci asta e tot? toate mesajele se encripteaza din broswer si se decripteaza din server?
- si faci o cerere si ti o accepta si asta e tot? toata smecheria?


1. **(18)** Setup a SSH server, generate a key and connect from your workstation.
- i connected from my host to my vm using ssh. i also added a key pair to automatically connect. was it ok?

_Encryption, Public and Private Keys, SSL/TLS Certificates, CSR (Certificate Signing Request), HTTPS, Secure Shell (SSH), Authentication, Key Exchange, Symmetric vs Asymmetric Encryption._

---

## 🧩 **Network Configuration & Management**

Tasks involving setup and configuration of network interfaces, routing, and hostnames.

1. **(17)** Configure a dummy interface and setup IP Forward (Linux).
- what is ip forward?
- what are examples of this interfaces. how do each work. are they rules? are they just algoriths
    
1. **(15)** Configure RDP on Windows 10 and Server 2016.
- so i understand this means remotely connecting to a gui. its like teamviewer?? 
- how does it work? when is it used? why is it used if i can use cmd

    
1. **(14)** Configure network interfaces using netsh.
- what even is a network interface. what are the types of network interface? what is it a file? what does it contain? what is it used for?
    
1. **(13)** Define and use Hostnames between machines.
- where is this information stored?
- where do we keep it
- is it only on lan? is it on dns?
    
1. **(16)** Setup a Hostname for your Windows machine and ping it.
- idk what windows machine u mean tho. what machine? like the one im on?
    
IP Addressing, Network Interfaces, Subnets, Routing, Hostnames, NAT (Network Address Translation), DHCP (Dynamic Host Configuration Protocol), VLAN (Virtual LAN), RDP (Remote Desktop Protocol), Windows & Linux Network Tools.

---

## 🌐 **Network Diagnostics & Analysis**

Tasks dealing with traffic capture, tracing, and connectivity verification.

1. **(9)** Create a filter to catch all packets during a connectivity test. Simulate a DNS request. Save all packets from eth0 in the file and open it for analysis. Identify your DNS request.
    
2. **(11)** Copy a web request done in browser and repeat it from the CLI.
    
3. **(10)** Download a page using Linux CLI.
    
4. **(6)** Identify applications that use internet connection at the moment.
    
5. **(4)** Check if there are no loss packets on path until [www.cisco.com](http://www.cisco.com).
    
6. **(3)** Discovery the network path until amazon.com.
    
7. **(5)** How much time do we need to reach [www.facebook.com](http://www.facebook.com)?
    
8. **(2)** Check if [www.google.com](http://www.google.com) domain is alive.
    
9. **(1)** Identify the IP address of endava.com.
    

→ TCP/IP Model, TCP vs UDP, ICMP (ping), Traceroute, DNS (Domain Name System), Routing, Subnet Masks, Packet Loss, Latency, Network Utilities (`ping`, `traceroute`, `nslookup`, `tcpdump`, `curl`), Wireshark (Packet Capture and Analysis).

---

## 💻 **System Information & Identification**

Tasks about identifying local network and system information.

1. **(7)** Identify DNS server configured on local PC.
    
2. **(8)** Identify MAC address of your device.

_→ MAC Addresses, ARP (Address Resolution Protocol), Network Interface Cards (NICs), DNS Servers, DHCP, IP Configuration Tools (`ipconfig`, `ifconfig`), OSI Model Layer 2 vs Layer 3 differences._





----
questions
1. so i wanna understand network interfaces. they are the connection between your pc and the network. but there is also network interfaces that are the connection to your pc tp ypur pc? what are the types? what is the difference? they can use different protocols right? so nat is a network interface? also i wanna understand what everything in the netstat command. like what do they mean? are they only the connectins that are toward smth else? are they the incoming requests?