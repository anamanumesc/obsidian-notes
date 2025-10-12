# **6. scripting and automation**

bash main.sh

- runs bash script file
    
- bash = bourne again shell
    

sleep 100 && echo 'done' &

- sleep = pause for given seconds (100 here)
    
- && = run next command only if previous succeeded
    
- & = run in background
    

jobs

- lists background jobs
    

fg 1

- brings job 1 to foreground
    
- fg = foreground
    

Ctrl+z

- suspends current foreground process
    

bg 1

- resumes job 1 in background
    
- bg = background
    

systemd

- init system and service manager
    
- manages startup, services, and logging  
    directories:  
    /etc/systemd/system/ -> custom system services  
    /run/systemd/system/ -> runtime services  
    /usr/lib/systemd/user/ -> user-level units
    

cron jobs

- scheduled repetitive tasks
    
- cron = from chronos (time)  
    directories:  
    /etc/cron.hourly -> hourly scripts  
    /etc/cron.daily -> daily scripts  
    /etc/cron.weekly -> weekly scripts  
    /etc/cron.monthly -> monthly scripts  
    /etc/cron.d -> custom cron definitions
    

crontab -l

- lists current user’s cron jobs
    
- crontab = cron table
    
- -l = list
    

crontab -e

- edit cron jobs
    

sudo crontab -u tom -l

- list cron jobs for specific user
    
- -u = user
    

cat /etc/passwd | awk 'BEGIN { FS = ":"} ;{ print $1}' | xargs -I % sudo crontab -u % -l

- lists cron jobs for all users
    
- awk splits file by ":" and prints first field (username)
    
- xargs executes crontab for each user
    
- -I % sets placeholder for input
    