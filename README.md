# OSCP_Prep_Tools
About OSCP Prepration And Useful Tools and Techniques:

  1. Tools:
        1. nmap 
        2. nikto
        3. gobuster
        4. dirb/wfuzz
        5. FTP
        6. SMBCLIENT
        7. Enum4Linux
        8. mount/unmount
        9. hydra
        10. wpscan
        11. metasploit
  2. Importatnt Script:
        1. linpeas.sh(https://github.com/carlospolop/PEASS-ng/tree/master/linPEAS)
        2. winpeas.sh/winpeas.exe(https://github.com/carlospolop/PEASS-ng/tree/master/winPEAS)
        3. powerup.ps1(https://github.com/PowerShellMafia/PowerSploit/blob/master/Privesc/PowerUp.ps1,
                       https://www.harmj0y.net/blog/powershell/powerup-a-usage-guide/)
  
  3. Vulnerability:
        1. LFI(https://highon.coffee/blog/lfi-cheat-sheet/)
        2. RCE/RFI(https://book.hacktricks.xyz/pentesting-web/file-inclusion,https://github.com/russweir/OSCP-cheatsheet/blob/master/File%20Inclusion.md)
        3. Log Poisoning(https://outpost24.com/blog/from-local-file-inclusion-to-remote-code-execution-part-1,https://www.hackingarticles.in/apache-log-poisoning-through-lfi/,https://shahjerry33.medium.com/rce-via-lfi-log-poisoning-the-death-potion-c0831cebc16d)
        4. FTP exploitation(https://pentestlab.blog/2012/03/01/attacking-the-ftp-service/,https://shahmeeramir.com/penetration-testing-of-an-ftp-server-19afe538be4b)
        5. SMB Exploitation
        6. NFS exploitation(https://book.hacktricks.xyz/pentesting/nfs-service-pentesting)
        7. CMS Exploitation
        8. port forwarding and port turnling attack(https://sushant747.gitbooks.io/total-oscp-guide/content/port_forwarding_and_tunneling.html,https://oscp.infosecsanyam.in/pivoting/tunneling-and-port-forwarding)
        9. SQL injection(https://sushant747.gitbooks.io/total-oscp-guide/content/sql-injections.html,https://github.com/codingo/OSCP-2/blob/master/Documents/SQL%20Injection%20Cheatsheet.md)
   4. Port Scanning Process:
        1. FTP
        2. SSH
        3. SMTP
        4. HTTP/HTTPS
        5. SMB
        6. RPC
        7. NFS
         
   5. Basics For Linux:
        1. Some Command for Beginner(https://www.tutorialspoint.com/unix/index.htm,)
   6. Linux Privilege Escalation Process:
        1. Check Configuration File
        2. Check "sudo -l" permission
        3. Check kernel Version
        4. Check group member permission
        5. Check Cron Job
        6. Check SUID permission
        7. Check Any file with editable permission but running through the root
        8. Check Weak Process 
   7. Windows Privilege Escalation Process:
        1. Check Kernel Exploitation
        2. Check weak service permission
        3. Check "Unquated Service Path"
        4. Check Stored Credentials
        5. Check "AlwaysElavated Install"
        6. Check User Permissions


1.TOOLS:
    1. nmap:
          this is the first command we have when we got the ip address of victim machine to scan the port and tried to find out which kind of service is running on the victim             system.
          
          Normal port scan:
              root@kali# nmap -sC -sV <IP_Address>
              
          Full Port Scan:
              root@kali# nmap -sC -sV <IP_Address> -p-
           
          With NSE scripts:
              root@kali# nmap --script=<script_name> -sC -sV <IP_Address> 

   2. Nikto:
           Nikto is tool for scanning the web app vulnerability.
           
           root@kali# nikto --help --> for help
           
           root@kali# nikto -h <http://ip> -->if port is 80/443
           
           root@kali# nikto -h http://ip:port --> if port is something else
           
           root@kali# nikto -h <ip_add> --useproxy <proxy_address_with_port>
           
           exam:
           root@kali# nikto -h 192.168.1.2 --useproxy http://192.168.1.2:3128
   3. gobuster:
           gobuster is a tool for bruteforce the directory and file which is not avialble directly.
           
           uses:
           root@kali# gobuster -h
           
           root@kali# gobuster dir --url http://192.168.1.3 -w /usr/share/dirbuster/directory-list-2.3-medium.txt
   4. dirb/wfuzz:
           same as gobuster.
   5. FTP:
           ftp for ftp login.
          
            root@kali# ftp 192.168..2.3 
            root@kali# nc ip port
   6. smbclient:
            for Enumeration Of SMB
            root@kli# smbclient -L //IP --> for see the share's
            
            root@kali# smbclient //IP/share_name -U username --> to access the share's
           
           
   7. Enum4linux:
            root@kali# enum4linux IP --> for gather all imformation about the SMB.
   8. RPC(111):
            from this port we can basically scan all the username and other data about the target.
            
            root@kali# rpclient IP_address
            rpc>help
   9. NFS:
            Network File System with the help this service we can share whole file system in the network.
            if it's vulnerable then we can mount the share and acess the share.
            --> command --> mount/unmount
  
  
  Windows Privilege escalation Cheatsheet:
            Link:
                  https://0xsp.com/offensive/privilege-escalation-cheatsheet
                  https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Windows%20-%20Privilege%20Escalation.md
                  https://sushant747.gitbooks.io/total-oscp-guide/content/privilege_escalation_windows.html
  Linux privilege Escalation cheat sheet:
            link:
                  https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/
                  https://johnjhacking.com/blog/linux-privilege-escalation-quick-and-dirty/
                  https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Linux%20-%20Privilege%20Escalation.md
                  https://www.hackingarticles.in/privilege-escalation-cheatsheet-vulnhub/
                  https://cheatography.com/blacklist/cheat-sheets/linux-windows-privilege-escalation/
