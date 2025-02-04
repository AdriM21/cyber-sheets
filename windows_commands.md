# Windows Commands

A list of useful Windows commands for cmd and powershell

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