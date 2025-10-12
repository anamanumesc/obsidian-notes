# **7. debugging and monitoring**

ps aux | grep name

- shows processes matching "name"
    
- ps = process status
    
- a = all users
    
- u = user-oriented format
    
- x = include background processes
    

tail -f /proc/PID/fd/1

- shows live standard output of process by id
    
- tail -f = follow output in real time
    

tail -f /proc/PID/fd/2

- shows live error output (stderr)
    

strace -pPID -s9999 -e write

- traces system calls and signals of a process
    
- -p = attach to process id
    
- -s = string length to print
    
- -e = filter by system call (write)
    
- strace = system trace
    

systemctl --failed

- lists failed services
    
- systemctl = system control
    

systemctl status SERVICE.service

- shows service status
    

journalctl -fu SERVICE.service

- view live logs of a service
    
- -f = follow
    
- -u = unit (service)
    
- journalctl = systemd journal logs
    

tail -f /var/log/SERVICE/SERVICE.log

- view specific service logs in real time
    

df -h

- check disk usage
    

ncdu /var/log

- analyze directory size interactively
    

lsof | grep deleted

- list open deleted files (still occupying space)
    

du /work -aBM 2>/dev/null | sort -nr | head -n 50 | more

- du = disk usage
    
- -a = all files
    
- -B = block size (MB here)
    
- sort -nr = sort numeric reverse
    
- head -n 50 = first 50 results
    
- more = view page by page
    

find /work -size +10M -ls

- find files larger than 10MB and list them
    

free -h

- shows free/used memory
    
- -h = human readable
    

htop, top, atop

- process and resource monitoring tools
    
- top = table of processes
    
- htop = improved interactive top
    
- atop = advanced top (detailed logging)
    
