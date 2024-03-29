ubuntu-conf  
===========
  
ubuntu_config.sh is a script to harden a Ubuntu server.  

It's meant to be run from the console, and directly after a server has been installed.      
  
Tested on Ubuntu Server 14.04 LTS.    

## Howto
Start the installation of the server.    
Pick language, keyboard layout, timezone and so on as you usually would.
Partition the system:    
/    
/boot (rw)    
/home (rw,nosuid,nodev)    
swap    
/var     
/var/log (rw,nosuid,nodev,noexec)    
/var/log/audit (rw,nosuid,nodev,noexec)   

Note that /tmp and /var/tmp will be added automatically by the script.

Do not add any packages.    
Log in.     
Download the script.     
Change the configuration options and last but not least run the script.    

##Configuration options
FW_ADMIN="192.168.2.100" *The IP address that will be able to connect with SSH.*  
SSH_GRPS="sudo" *Which group the users have to be member of in order to acess via SSH.*  
FW_CONF="https://raw.githubusercontent.com/konstruktoid/ubuntu-conf/master/net/firewall.conf" *Skeleton firewall configuration*  
FW_POLICY="https://raw.githubusercontent.com/konstruktoid/ubuntu-conf/master/net/firewall" *Skeleton firewall configuration*  
SYSCTL_CONF="https://raw.githubusercontent.com/konstruktoid/ubuntu-conf/master/misc/sysctl.conf " *Stricter sysctl settings*  
AUDITD_RULES="https://raw.githubusercontent.com/konstruktoid/ubuntu-conf/master/misc/audit.rules" *Auditd rules*    
VERBOSE="N" *If you want all the details or not*     
CHANGEME="" *Add something just to verify that you actually glanced the code*    
      
##Recommended reading:  
Red Hat 6 STIG - Version 1 Release 4    
Guide to the Secure Configuration of Red Hat Enterprise Linux 5    
CIS Ubuntu 12.04 LTS Server Benchmark v1.0.0    
https://wiki.ubuntu.com/Security/Features     
https://help.ubuntu.com/community/StricterDefaults        


