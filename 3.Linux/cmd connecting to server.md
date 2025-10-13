

ssh -i ~/.ssh/private_key user@host:port

- connects to remote server using ssh (secure shell)
    
- -i = identity file (private key)
    
- default port 22
    

ssh-keygen -t rsa -q -P "" -f $KEY_NAME

- generates new ssh key pair (public/private)
    
- -t = type (rsa = Rivest–Shamir–Adleman encryption)
    
- -q = quiet mode (no output)
    
- -P = passphrase ("" means none)
    
- -f = file name for key
    

who

- shows users currently logged in
    
- who = who is logged in
    

echo "Hi Folks! I'm ${USER}." | wall

- wall = write all, sends message to all logged in users
    
- ${USER} = current username variable
    
- | = pipe, sends output to next command
    

df -h

- shows disk space usage
    
- -h = human-readable
    
- df = disk free
    

htop

- interactive process viewer (cpu/ram usage)
    
- improved version of top (table of processes)
    

netstat -nltp

- shows active ports and processes
    
- -n = show numbers (no names)
    
- -l = listening sockets
    
- -t = tcp connections
    
- -p = process id/program
    
- netstat = network statistics
    

lsb_release -a

- shows linux distribution info
    
- -a = all details
    
- lsb = linux standard base
    