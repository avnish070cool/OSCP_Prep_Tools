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
        1. linpeas.sh
        2. winpeas.sh/winpeas.exe
        3. powerup.ps1
  
  3. Vulnerability:
        1. LFI
        2. RCE/RFI
        3. Log Poisoning
        4. FTP exploitation
        5. SMB Exploitation
        6. NFS exploitation
        7. CMS Exploitation
        8. port forwarding and port turnling attack
        9. SQL injection
   4. Port Scanning Process:
        1. FTP
        2. SSH
        3. SMTP
        4. HTTP/HTTPS
        5. SMB
        6. RPC
        7. NFS
         
   5. Basics For Linux:
        1. Some Command for Beginner
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
   3. 
