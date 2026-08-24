# Basic File Management

In linux we can manager files directly from the terminal, using commands like ls, cd, mkdir, touch and rm.

> ls > list directories, is used to list directories this command can take arguments.
* Synopsis : ls [OPTION]... [FILE]...
```bash
#Shell output
[xhanti@localhost ~]$ ls 
Desktop    Downloads  Pictures  Templates  wazuh-install-files.tar
Documents  Music      Public    Videos     wazuh-install.sh
```
> ls arguments

```bash
#List files with details.
ls -l
```
List files in a [human readable format](./Introduction-to-the-shell.md#human-readable-format) that's easier to read.
```bash
ls -lh 
# Adding (a) to the ls command shows hidden folders and files.
ls -lha
```
---
> mkdir > Make directory, is used to make a new directory this command takes arguments.
* Synopsis : mkdir [OPTION]... DIRECTORY...
```bash
# mkdir followed by the folder you'd like to creates the folder.
[xhanti@localhost Documentation]$ mkdir foo

# If you create a folder that already exists it'll give you a error.
[xhanti@localhost Documentation]$ mkdir foo
mkdir: cannot create directory ‘foo’: File exists

# Using -p lets make fail gracefully and doesn't throw a error.
[xhanti@localhost Documentation]$ mkdir -p foo

# flag v (verbose) prints a message for each created directory.
[xhanti@localhost Documentation]$ mkdir -pv foo

#Creating, copying, moving and renaming files.
[xhanti@localhost ~]$ touch test
[xhanti@localhost ~]$ ls -lha
total 248K
drwx------. 16 xhanti xhanti 4.0K Aug 24 14:37 .
drwxr-xr-x.  3 root   root     20 Aug 18 13:27 ..
-rw-------.  1 xhanti xhanti  587 Aug 24 13:33 .bash_history
-rw-r--r--.  1 xhanti xhanti   18 Feb 15  2024 .bash_logout
-rw-r--r--.  1 xhanti xhanti  141 Feb 15  2024 .bash_profile
-rw-r--r--.  1 xhanti xhanti  492 Feb 15  2024 .bashrc
drwx------. 11 xhanti xhanti 4.0K Aug 18 15:43 .cache
drwx------. 10 xhanti xhanti 4.0K Aug 24 10:41 .config
drwxr-xr-x.  2 xhanti xhanti    6 Aug 18 13:39 Desktop
drwxr-xr-x.  2 xhanti xhanti    6 Aug 18 13:39 Documents
drwxr-xr-x.  2 xhanti xhanti    6 Aug 18 13:39 Downloads
drwxr-xr-x.  2 xhanti xhanti    6 Aug 18 13:39 Music
drwxr-xr-x.  2 xhanti xhanti   53 Aug 18 15:59 Pictures
drwxr-xr-x.  2 xhanti xhanti    6 Aug 18 13:39 Public
drwxr-xr-x.  4 xhanti xhanti   71 Aug 24 13:34 RedHat-Enterprise-Liniux-
drwx------.  2 xhanti xhanti   88 Aug 24 13:34 .ssh
drwxr-xr-x.  2 xhanti xhanti    6 Aug 18 13:39 Templates
-rw-r--r--.  1 xhanti xhanti    0 Aug 24 14:37 test
drwxr-xr-x.  2 xhanti xhanti    6 Aug 18 13:39 Videos

#copy files or directories if a directory is what your copying end the folder name with a forward slash
[xhanti@localhost ~]$ mv test Documents/
#If we ls the directory we can see the the test file in the Documents directory.
[xhanti@localhost ~]$ ls Documents/
test

# Cding into the folder allows us to view and edit the file.
[xhanti@localhost ~]$ cd Documents/

#Rename test to test.txt
[xhanti@localhost Documents]$ mv test test.txt
[xhanti@localhost Documents]$ ls
test.txt

# We can also use *echo* to create files and add contents to that file all in one line.
[xhanti@localhost ~]$ echo "This is an example, smile :)" > test-smile.txt
[xhanti@localhost ~]$ ls -lha
total 252K
drwx------. 16 xhanti xhanti 4.0K Aug 24 14:51 .
drwxr-xr-x.  3 root   root     20 Aug 18 13:27 ..
-rw-------.  1 xhanti xhanti  587 Aug 24 13:33 .bash_history
-rw-r--r--.  1 xhanti xhanti   18 Feb 15  2024 .bash_logout
-rw-r--r--.  1 xhanti xhanti  141 Feb 15  2024 .bash_profile
-rw-r--r--.  1 xhanti xhanti  492 Feb 15  2024 .bashrc
drwx------. 11 xhanti xhanti 4.0K Aug 18 15:43 .cache
drwx------. 10 xhanti xhanti 4.0K Aug 24 10:41 .config
drwxr-xr-x.  2 xhanti xhanti    6 Aug 18 13:39 Desktop
drwxr-xr-x.  2 xhanti xhanti   22 Aug 24 14:46 Documents
drwxr-xr-x.  2 xhanti xhanti    6 Aug 18 13:39 Downloads
drwxr-xr-x.  2 xhanti xhanti    6 Aug 18 13:39 Music
drwxr-xr-x.  2 xhanti xhanti   53 Aug 18 15:59 Pictures
drwxr-xr-x.  2 xhanti xhanti    6 Aug 18 13:39 Public
drwxr-xr-x.  4 xhanti xhanti   71 Aug 24 13:34 RedHat-Enterprise-Liniux-
drwx------.  2 xhanti xhanti   88 Aug 24 13:34 .ssh
drwxr-xr-x.  2 xhanti xhanti    6 Aug 18 13:39 Templates
#There's our test smile file :)
-rw-r--r--.  1 xhanti xhanti   29 Aug 24 14:51 test-smile.txt
drwxr-xr-x.  2 xhanti xhanti    6 Aug 18 13:39 Videos
#cp -> copy the file to Documents
[xhanti@localhost ~]$ cp test-smile.txt Documents/
[xhanti@localhost ~]$ ls Documents/
test-smile.txt  test.txt
#cat so we see the contents of the file and adding the path of the file and the file.
[xhanti@localhost ~]$ cat Documents/test
test-smile.txt  test.txt        
[xhanti@localhost ~]$ cat Documents/test-smile.txt 
This is an example, smile :)
 
```

> [!WARNING] 
> Destructive commands
```bash
[xhanti@localhost ~]$ ls
Desktop    Music     RedHat-Enterprise-Liniux-  Videos
Documents  Pictures  Templates                  wazuh-install-files.tar
Downloads  Public    test-smile.txt             wazuh-install.sh

#If you run rm it can delete files alone but not folders
[xhanti@localhost ~]$ rm test-smile.txt 
[xhanti@localhost ~]$ mkdir -p foo
[xhanti@localhost ~]$ ls 
Desktop    foo       Public                     Videos
Documents  Music     RedHat-Enterprise-Liniux-  wazuh-install-files.tar
Downloads  Pictures  Templates                  wazuh-install.sh
[xhanti@localhost ~]$ rm -r foo/
[xhanti@localhost ~]$ rm -ri Documents/
rm: descend into directory 'Documents/'? no
```



---
> cd > Change directories, is used to change from one directory to another, this command can take arguments.
* Synopsis : cd [-L | -P] [dir]
```bash
#Shell output
[xhanti@localhost ~]$ cd Downloads/
[xhanti@localhost Downloads]$ 
```
---
---
