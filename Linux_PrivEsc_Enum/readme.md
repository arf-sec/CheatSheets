# Early Information Gathering, Linux Environment

`id`
- gather information about current user

`cat /etc/passwd`
- enumerate users on machine
```
cat /etc/issue
cat /etc/*-release
uname -a
```
- enumerate system information

`ps -aux`
- list processes in user readable (u) format with and without tty (a,x)
```
ifconfig -a
ip a
```
- a flag displays all information
- display network configurations

`route (or routel)`
- routing table information
```
netstat -anp
netstat -nat
netstat -ano
ss -anp
```
- a to avoid hostname resolution, n to list process name, p to list process names
- both tools list network connections

`iptables`
- list firewall rules (with ROOT privileges)

`grep -Hs iptables /etc/*`
- look for any backups or save instances of iptables 
- can be done as a non-root user

`/etc/cron*`
- lists scheduled tasks
- for example, /etc/cron.daily is for daily tasks
- system admins also place their own jobs in /etc/crontab
- examine privileges for cronjobs

`dpkg -l`
- list Debian-installed package

`rpm`
- package manager used by Red Hat
- not sure how to list packages, maybe -l?

`find / -writable -type d 2>/dev/null`
- Find writable directories from root directory onward.  

`mount`
- List all mounted filesystems

`/etc/fstab`
- contains info about all drives mounted at boot time

`/bin/lsblk`
- view all available disks

`lsmod`
- list loaded kernel modules

`/sbin/modinfo libata`
- to find out more info about libata driver

`find / -perm -u=s -type f 2>/dev/null`
- SUID marked binaries
- basically, commands that can be run as root

`driverquery /v`
- list drivers installed on system
