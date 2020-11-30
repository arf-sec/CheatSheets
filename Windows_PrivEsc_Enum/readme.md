# Early Information Gathering, Windows Environment

**SYSTEM ENUMERATION**

`systeminfo`
- basic command to gather information about the system

`systeminfo | findstr /B /C:"OS Name" /C:"OS Version" /C:"System Type"`
- example of using findstr to pull specific info from systeminfo

`hostname`
- cmd for hostname

`wmic qfe`
- returns info about system
- may return patch levels

`wmic logicaldisk`
- disk and drive info

`wmic localdisk get caption,description,providername`
- cleaner localdisk output for quick interpretation

`tasklist /SVC`
`tasklist /V`
- running services and programs

**USER ENUMERATION**
```
whoami
whoami /priv
whoami /groups
net user
```
- users on machine
- can also try net user Administrator

`net localgroup`
- group enum

**NETWORK ENUMERATION**
```
ipconfig
ipconfig /all
arp -a 
route print
netstat -ano (for ports)
```

**PASSWORD HUNTING**
```
findstr /si password *.txt
findstr /si password *.txt *.ini *.config *.xml

netsh wlan show profile
netsh wlan show profile (network name) key=clear
```

**AV & FIREWALL ENUMERATION**

`sc query`
- service control query

`sc query windefend`
- query to see if windows defender is running

`sc queryex type= service`
- list services

`netsh advfirewall firewall dump`
- may return nothing

`netsh firewall show state`
- checkin' the FW
