a broad term
- connection point between your laptop and a connection
- a _software representation_ of how your computer talks to a network
- there are multiple types of interfaces
you see all of them when u run ip addr show
- each interface has a ip address assigned
- u can ping it. ping = send icmp packets
- on linux, each interface has: a name,, a mac address, one or more ip addresses, a state, associated routes
- it’s your **computer’s doorway** into _whatever network it’s attached to_.

![[Pasted image 20251019221452.png]]

![[Pasted image 20251018224914.png]]

virtual interface:
loopback
vpn


physical interface:
wifi card
ethernet




Each interface can have:

- An **IP address**
    
- A **subnet mask**
    
- A **gateway**
    
- A **DNS configuration**
    
- A **MAC address**