
nc -l PORT

- opens listener on specified port
    
- nc = netcat (network concatenation)
    

python3 -m http.server PORT

- simple http server for current directory
    
- -m = module mode
    

ifconfig

- shows network interface info
    
- ifconfig = interface configuration
    

ip addr

- shows ip addresses and interfaces
    
- ip = iproute2 utility
    

curl ifconfig.io

- get public ip address
    
- curl = client url (transfer data via URL)
    

curl localhost:PORT

- test connection to local service
    

curl PRIVATE_IP:PORT  
curl PUBLIC_IP:PORT

- test remote service reachability
    

telnet PRIVATE_IP PORT

- test tcp connectivity
    
- telnet = terminal network
    

route -n

- display routing table
    
- -n = numeric addresses
    

ip route

- show routing table (modern replacement for route)
    

netstat -rn

- show routing table with numeric output
    

iptables -L

- lists firewall rules
    
- -L = list
    
- iptables = ip packet filter tables
    

netstat -nltp

- shows all listening ports and processes
    

dig unix.stackexchange.com

- dns lookup for domain
    
- dig = domain information groper