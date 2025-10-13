trei tipuri de useri:
1. root - userul suprem, are UID 0, access total la sistem 
2. user normal - 
3. user de sistem - daemon, syslog, www-data - folositi de servici

sunt definiti in /etc/passwd
parolele lor criptate in /etc/shadow
grupurile in /etc/groups


cd ~ or cd  -> go to home diretory



----
comenzi


sudo useradd -m ${NEW_USER}

- creates new user with home directory
    
- -m = make home directory
    
- useradd = add user
    

nano /home/${NEW_USER}/.ssh/authorized_keys

- opens file to add ssh key for user login
    
- nano = simple terminal text editor (from "Nano’s ANOther editor")
    

sudo visudo

- opens sudoers file safely for editing
    
- visudo = view sudo, edits permissions
    

cat /etc/sudoers | grep tom

- shows lines in sudoers file containing "tom"

- cat = concatenate (display content)
    
- grep = global regular expression print, searches text
    

sudo chown tom:tom file.out

- changes ownership to user:group tom
    
- chown = change owner
    

sudo usermod -aG docker tom

- adds user tom to docker group
    
- -a = append
    
- -G = group
    
- usermod = modify user
    

chmod

- changes permissions of files
    
- chmod = change mode
    
- numbers mean: 4 read, 2 write, 1 execute  
    examples:  
    chmod 777 file.out → all full access  
    chmod 755 file.out → owner rwx, others r-x  
    chmod 644 file.out → owner rw, others r  
    chmod +x file.out → add execute permission  
    chmod 400 file.pem → owner read only
    

ls -al

- lists all files with details
    
- -a = all (includes hidden)
    
- -l = long listing
    
- ls = list
    

who

- shows who’s logged in
    

wall

- broadcast message to all users
    
- wall = write all
    

write tom

- send message directly to user tom
    