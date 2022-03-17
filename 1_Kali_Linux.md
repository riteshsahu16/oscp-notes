
## Booting up Kali linux
- **passwd**  : change password
    - ``` $ passwd  ``` 
    
- **whoami** : get user
    - ```$ whoami```

## Kali Menu

## Kali Documentation
    - http://docs.kali.org
    - https://forums.kali.org
    - https://tools.kali.org

## Finding your way around Kali
- Linux File System
    * /bin : basic programs(ls, cd, cat, etc.)
    * /sbin : system programs(fdisk, sysctl, etc.)
    * /etc : Configuration files(apache, network manager, ssh, etc.)
    * /tmp : temporary files (typically deleted on boot)
    * /usr/bin : application (nmap, ncat, apt, etc.)
    * /usr/share : application support & data files

- Basic Linux commands
    * **man** Command : provide documentation
        - eg.
            ``` $ man ls ```
        - Perform keyword search with -k option
            ``` $ man -k passwd
        - Narrow search with regular expression
            - ``` $ man -k '^passwd$' ```
            - ``` $ man 5 passwd ```

    * **apropos** : helpful for finding commands based on description
        - ``` $ apropose partition ```
    
    * **ls** : Listing files 
        - Options : -a : list all, -1 : display each file on single line
            - ``` $ ls /Downloads -a1 ```
            - ``` $ ls /Documents/*.conf ```
    
    * Moving Around
        - **cd** : change directory
            ``` $ cd /usr/share ```
        - **pwd** : present working directory
            ``` $ pwd ```
        - **cd** ~ : return to home directory
            - ``` $ cd ~ ``` 
            - ``` $ pwd ```
    
    * Creating Directories
        - **mkdir** : creates folder
            - ``` $ mkdir Notes ```
        - when using spaces in between name 
            - ``` $ mkdir module one ```
            - ``` $ rm -rf module/ one/ ```
        - **mkdir -p** : make multiple directories
            - ``` $ mkdir -r test/{recon, exploit, report} ```
    
- Finding files 
    - **which** : searches through the directorie, If a match is found, which returns   the full path to the file
        - ``` $ which $PATH ```

    - **locate** : searches in in-built database locate.db. 
        - ``` $ sudo updatedb ```  
        - ``` $ locate sbd ```

    - **find** : search by file name, age, size, owner, file type, timestamp, permissions, and more
        - ``` $ sudo find / -name sbd* ```
        
## Managing Services
- **systemctl** 
    * start a service 
        - ``` $ sudo systemctl start ssh ```
    * to verfify service is running
        - ``` $ sudo ss -antlp | grep sshd ``` 
    * to make service automatically start
        - ``` $ sudo systemctl enable ssh ```
    * list all available services
        - ``` $ systemctl list-unit-files ```    
            
# Searching, Installing & Removing Tools
- **apt**
    - Update APT Repository
        - ``` $ sudo apt update ```
    - Upgrade distribution
        - ``` $ sudo apt dist-upgrade ```
    - Upgrade particular package
        - ``` $ sudo apt upgrade metasploit-framework ```
    - Searching for package in apt-cache [searches for keyword in package-description]
        - ``` $ apt-cache search pure-ftpd ```
    - Show package description
        - ``` $ apt show resource-agents ```
    - Installing a package
        - ``` $ sudo apt install pure-ftpd ```
    - Remove package but keep configuration file
        - ``` $ sudo apt remove pure-ftpd ```
    - Remove package completely
        - ``` $ sudo apt remove --purge pure-ftpd ```

- **dpkg** 
    - when package is already downloaded or obtained in some other way
        - ``` $ sudo dpkg -i man-db_amd64.deb ```  


        