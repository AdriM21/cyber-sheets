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

## bash

#### Shell Operators

```
*_command* &
```

* Executes \_command in background

```
*_command1* && *_command2*
```

* Executes \_command1 and \_command2 at the same time

```
*_command* > *_file*
```

* Executes \_command and writes its result in \_file

```
*_command* >> *_file*
```

* Executes \_command and appends its result to \_file

```
*_command1* | *_command2*
```

* Executes \_command1 and then pass its output to executes \_command2