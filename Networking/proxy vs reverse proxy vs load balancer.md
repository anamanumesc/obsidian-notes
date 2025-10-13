
also proxy vs vpn?

# forward proxy
middleman between u and the internet
it forwards the requests u have
you can protect the company network
all internet is routed trough a proxy
block some websites
scan the response and block them if suspicious
it logs peoples activity
also it cashes locally 

# reverse proxy -ngnix
sits on the server side
handles incoming requests from clients
it also has the functionality of load balancing
protects the servers
logging

# load balancer
distributing incoming traffic accross multiple servers to balance the load

# cloud load balancer
you need both:
1. cloud load balancer outside of servers
2. entrypoint into private network

![[Pasted image 20251013151612.png]]