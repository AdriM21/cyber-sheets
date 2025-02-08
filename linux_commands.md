# Linux Commands

A list of useful Linux commands for bash

## bash

#### Basics

```
pwd
```

* Displays current directory

```
ls *args*
```

* args:
	* *none*: displays current directory content
	* -lachs -1 --color=auto: displays current directory content with hidden, details and colors

```
cd *args*
```

* args:
	* X: sets current directory at "X"

```
touch *args*
```

* args:
	* X: creates file "X"

```
mkdir *args*
```

* args:
	* X: creates directory "X"

```
cat *args*
```

* args:
	* X: displays content of file "X"

```
cat >> X << EOF
Y
EOF
```

* Appends line "Y" at the end of file "X"

```
wc *args*
```

* args:
	* -l X: counts the number of lines in file "X"

```
echo *args*
```

* args:
	* X: outputs "X" text

```
less *args*
```

* args:
	* X: displays a part of file "X"

```
find *args*
```

* args:
	* X: name of the path to search from
	* -type X: sets the type of file to found to "X"
	* -name "X": sets the file name to find to "X"

```
mv *args*
```

* args:
	* X: file to move
	* Y: new location

```
cp *args*
```

* args:
	* X: file to copy
	* Y: copy location

```
rm *args*
```

* args:
	* -rf X: recursively removes file/directory "X"

```
file *args*
```

* args:
	* X: determines the type of file "X"

```
grep *args*
```

* args:
	* -lir -e "X": recursively lists all files which contains the expression "X", non-case sensitive and starting from the current folder

#### Shell Operators

```
*command* &
```

* Executes command in background

```
*command1* && *command2*
```

* Executes command1 and command2 at the same time

```
*command* > *file*
```

* Executes command and writes its result in file

```
*command* >> *file*
```

* Executes command and appends its result to file

```
*command1* | *command2*
```

* Executes command1 and then pass its output to executes command2

#### Compression & Uncompression

```
unzip *args*
```

* args:
	* X: unzips file "X"
	* -d Y X: unzips file "X" in directory pointed by path "Y"

```
7z *args*
```

* args:
	* x X: unzips file "X"

```
gzip *args*
```

* args:
	* -d X: unzips file "X"

```
unrar *args*
```

* args:
	* x X: unrars file "X"

```
tar *args*
```

* args:
	* -xf X: untars file "X"

#### Network

```
ip a s
```

* Displays IP addresses info

```
host
```

* Displays IP addresses info

```
ifconfig
```

* Displays network interfaces

```
netstat -antp
```

* Lists TCP connections

```
ping *args*
```

* args:
	* X: pings IP "X"
	* -c X: limits scan to "X" requests
	* -b: broadcasts to subnet

```
traceroute *args*
```

* args:
	* X: traces the route to IP "X"

```
wget *args*
```

* args:
	* X: downloads a file on a server with URL "X"

```
curl *args*
```

* args:
	* http://X/: downloads the web page at IP "X"
	* -L http://Y/X/: downloads the web page at IP "X" with redirections "Y"

```
git *args*
```

* args:
	* clone X: clone git repo from IP "X"

#### Processes

```
echo $0
```

* Displays info about current shell

```
ps *args*
```

* args:
	* *none*: displays current user's running processes
	* aux: displays all running processes

```
top
```

* Lists processes with performance analytics

```
kill *args*
```

* args:
	* X: kills process with PID "X"

```
systemctl *args*
```

* args:
	* start X: starts service "X"
	* stop X: stops service "X"
	* enable X: enables service "X"
	* disable X: disables service "X"
	* status X: displays status of service "X"

```
fg *args*
```

* args:
	* X: gets to foreground the background process with PID "X"

#### Privileges

```
chmod *args*
```

* args:
	* +x X: gives the execution right to file "X"

```
su *args*
```

* args:
	* X: switch to user "X"

```
sudo *args*
```

* args:
	* *command*: executes command with super user's privileges
	* -l: displays accessible sudo commands for current user
	* -l -l: displays accessible sudo commands for current user

#### Some Executions

```
> vim X (opens file X with vim text editor)
	> 'i' (insertion is now available)
	> 'esc' (got to command line interface)
	> ':wq' (saves and quits)
```

```
> nano X (opens file X with nano text editor)
	> 'ctrl + o' (saves)
	> 'ctrl + x' (quits)
```

```
> subl X (opens file x with Sublime Text text editor)
```

```
python X.py
```

* Executes the python script called "X.py"