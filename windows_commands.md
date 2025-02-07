# Windows Commands

A list of useful Windows commands for cmd, powershell and AD

## cmd

#### Basics

```
cd *args*
```

* args:
	* *none*: displays current directory path
	* /p/: follows path *p* and sets a new current directory

```
dir *args*
```

* args:
	* *none*: lists content of current directory
	* /a: lists content and hidden content of current directory
	* /s: lists content of current and sub-directories

```
tree *args*
```

* args:
	* *none*: visualizes directories as a tree
	* -L 3 -d: lists current directory as a tree of depth 3

```
mkdir *args*
```

* args:
	* X: creates a new directory called "X"

```
rmdir *args*
```

* args:
	* X: removes the directory called "X"

```
type *args*
```

* args:
	* X: displays the content of the file called "X"

```
more *args*
```

* args:
	* X: displays the content of the file called "X" but on a maximum of 1 window size

```
copy *args*
```

* args:
	* X Y: copies the file called "X" to "Y" location

```
move *args*
```

* args:
	* X Y: moves the file called "X" to "Y" location

```
del *args*
```

* args:
	* X: deletes the file called "X"

```
erase *args*
```

* args:
	* X: erases the file called "X"

```
find *args*
```

* args:
	* X: finds string "X"

```
cls *args*
```

* args:
	* *none*: clears display

```
help *args*
```

* args:
	* *none*: displays help menu

```
shutdown *args*
```

* args:
	* /s: shutdowns the current device
	* /r: reboot the current device
	* /a: cancel the shutdown of the current device

#### Pipeline

```
*command_1* | *command_2*
```

* Executes command_1 and pass its output to execute command_2

```
*command_1* | more
```

* Executes command_1 and displays its output on several window pages

#### Processes

```
tasklist *args*
```

* args:
	* *none*: displays process list
	* /FI "imagename eq sshd.exe": displays process related to sshd.exe

```
taskkill *args*
```

* args:
	* /PID X: kills process with PID "X"

#### Information

```
set *args*
```

* args:
	* *none*: displays current configuration

```
ver *args*
```

* args:
	* *none*: displays OS version

```
systeminfo *args*
```

* args:
	* *none*: displays system info

#### Network

```
ipconfig *args*
```

* args:
	* *none*: displays current network configuration
	* /all: displays all current network configuration

```
ping *args*
```

* args:
	* X: pings server at IP address "X"

```
tracert *args*
```

* args:
	* X: traces route to server at IP address "X"

```
nslookup *args*
```

* args:
	* X: DNS lookup for server at IP address "X"

```
netstat *args*
```

* args:
	* *none*: displays current network connections
	* -abon: displays detailed current network connections

#### Disk and drivers

```
chkdsk *args*
```

* args:
	* *none*: checks the file system and disk volumes for errors and bad sectors

```
driverquery *args*
```

* args:
	* *none*: displays a list of installed device drivers

```
sfc *args*
```

* args:
	* /scannow: scans system files for corruption and repairs them if possible

#### Execution

```
powershell *args*
```

* args:
	* *none*: launchs a powershell session
	* -ep bypass -c ". .\x; x": executes command "x" in a powershell session

```
runas.exe *args*
```

* args:
	* /user:X Y: executes command "Y" with user "X" privileges

## powershell

#### Basics

```
Set-Location *args*
```

```
cd *args*
```

* args:
	* /p/: follows path *p* and sets a new current directory

```
Get-ChildItem *args*
```

```
DIR *args*
```

* args:
	* *none*: lists content of current directory
	* -Path "X": lists content of directory after path "X"

```
New-Item *args*
```

* args:
	* -Path "X": location of the new item
	* -ItemType "Y": creates a new item of type "Y"

```
Remove-Item *args*
```

* args:
	* -Path "X": location of the deleted item

```
Copy-Item *args*
```

* args:
	* -Path "X": location of the initial item
	* -Destination "Y": location of the copied item

```
Move-Item *args*
```

* args:
	* -Path "X": location of the initial item
	* -Destination "Y": location of the copied item

```
Get-Content *args*
```

* args:
	* -Path "X": location of the item to display its content

```
Select-String *args*
```

* args:
	* -Path "X": location of the item
	* -Pattern "X": find strign "X" in the item

```
Get-Command *args*
```

* args:
	* -CommandType "X": lists available commands of type "X"
	* -Name "X*": lists available commands that begins with "X"

```
Get-Help *args*
```

* args:
	* "X": gets help for command "X"

```
Get-Alias
```

* Lists all available aliases

```
Find-Module *args*
```

* args:
	* -Name "X": finds if a module called "X" exists on the net

```
Install-Module *args*
```

* args:
	* -Name "X": installs a module called "X" from the net

```
Clear
```

* Clears display

#### Pipeline

```
*command_1* | *command_2*
```

* Executes command_1 and pass its output to execute command_2

#### Information

```
Get-ComputerInfo
```

* Displays computer info

```
Get-LocalUser
```

* Displays local user

```
Get-NetIPConfiguration
```

* Displays IP config

```
Get-NetIPAddress
```

* Displays IP address

```
Get-Process
```

* Displays processes

```
Get-Service
```

* Displays services

```
Get-NetTCPConnection
```

* Displays TCP connections

```
Get-FileHash *args*
```

* args:
	* -Path "X": displays the hash of the file located at "X"

#### Execution

```
Invoke-Command *args*
```

* args:
	* *description*: executes commands on remote systems
	* -ComputerName "X": the name of the remote system
	* -Credential "X\Y": the credentials to connect to the remote system (username\password)
	* -ScriptBlock { X }: the command to execute

## AD

#### Basics

```
Set-ADAccount Password *account_name* -Reset -NewPassword (Read-Host -AsSecureString -Prompt 'New Password') -Verbose
```

* Resets account_name's password in AD

```
Set-ADUser -ChangePasswordAtLogon $true -Identity *account_name* -Verbose
```

* Forces a password reset at next login of account_name

```
gpupdate /force
```

* Forces a GPO update