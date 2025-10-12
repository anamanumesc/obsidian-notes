# **5. package management**

sudo apt update

- updates list of available packages from repositories
    
- apt = advanced package tool
    

sudo apt upgrade

- upgrades all installed packages to latest versions
    

dpkg -l python* | grep language

- lists all packages matching "python*" and filters by "language"
    
- dpkg = debian package manager
    
- -l = list installed packages
    
- grep = global regular expression print
    

sudo apt install ncdu -y

- installs ncdu package automatically
    
- -y = assume yes for all prompts
    

sudo apt remove ncdu -y

- removes ncdu package
    

sudo apt autoremove

- removes unused dependencies
    

sudo apt autoclean

- removes old cached package files
    

man grep

- shows manual page for grep
    
- man = manual
    

which python

- shows full path of binary being executed
    
- which = find program location in PATH
    

type -a python3

- displays how the shell interprets the command
    
- -a = all locations found
    
- type = show command type (builtin, alias, or file path)
    

readlink -f /usr/bin/python3

- shows absolute path of target file if symbolic link
    
- -f = follow symlinks
    
- readlink = display file link info
    
