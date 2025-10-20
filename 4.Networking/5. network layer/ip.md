ip privat - folosit de alte device-uri din reteaua LAN
ip public - nat . ruter . internet

ipv4 vs ipv6

---
# ipv6
ipv6 is not public or private. there is no nat

- not widely accepted by community
- 

# ipv4


---
# network part

part that belongs to the network. fixed
cat de lung e acest mask atat de ;lung e network part
they belon gin the same network / subnet 
#  host part

part that coresponds to the hosts

---
# private ip

Your **router** assigns it (using DHCP).
- Your router itself gets **one public IP** (from your Internet provider).
a specific range


# public ip 
Your **ISP** assigns it to your router.


----

# router 
Routers sit _between_ networks.  
That means they have **at least two IP addresses**:

1. **Private-side (LAN)** → example `192.168.1.1`

    - This connects to your local home network 
    - It shares the first three octets (`192.168.1`) with your devices.
    - Your phone/laptop use it as the **gateway**
    
2. **Public-side (WAN)** → example `81.23.45.6`

    - This connects to your ISP and the Internet. 
    - It’s completely different from the private network.



When you go online, your router uses **NAT (Network Address Translation)** to make all your devices appear as **one public IP**.






---




is this the case. the same network like nam wan? the same router? who gives this ip? is this the case for public or private. which has this split? public or private?? who makes this split? how does it work in my apartament? we all have the same network? how do we decide the size of the mask.
	


1. how does the router know where to send my package? im on my laptop and i type youtube. my ip address goes to the router. u said the router knows where to send it only based on the network part of the address. but that doesnt make sense. how does it know if my request is asking for something from the lan. and it doesnt need to exit the lan. or maybe im asking for a video from canada.
2. 
3. 