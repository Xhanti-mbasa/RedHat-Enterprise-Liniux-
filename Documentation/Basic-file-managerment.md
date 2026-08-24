# Basic File Management

In Linux, we can manage files directly from the terminal using commands such as `ls`, `cd`, `mkdir`, `touch`, `cp`, `mv`, and `rm`.

> `ls` → **List directory contents**. This command is used to list files and directories and can take arguments.
>
> **Synopsis:** `ls [OPTION]... [FILE]...`

```bash
# Shell output
[xhanti@localhost ~]$ ls
Desktop    Downloads  Pictures  Templates  wazuh-install-files.tar
Documents  Music      Public    Videos     wazuh-install.sh
```

### `ls` Arguments and Options

```bash
# List files with detailed information.
ls -l
```

List files in a [human readable format](./Introduction-to-the-shell.md#human-readable-format), which makes file sizes easier to read.

```bash
ls -lh
```

Adding `a` to the `ls` command shows hidden files and directories.

```bash
ls -lha
```

---

> `mkdir` → **Make directory**. This command is used to create new directories and takes directory names as arguments.
>
> **Synopsis:** `mkdir [OPTION]... DIRECTORY...`

```bash
# mkdir followed by the name of the directory you want to create.
[xhanti@localhost Documentation]$ mkdir foo

# If you create a directory that already exists, you will get an error.
[xhanti@localhost Documentation]$ mkdir foo
mkdir: cannot create directory ‘foo’: File exists

# Using -p prevents an error if the directory already exists.
[xhanti@localhost Documentation]$ mkdir -p foo

# The -v (verbose) option prints a message for each created directory.
[xhanti@localhost Documentation]$ mkdir -pv foo
```

### Creating, Copying, Moving, and Renaming Files

We can use `touch` to create an empty file.

```bash
[xhanti@localhost ~]$ touch test
```

We can then use `ls -lha` to verify that the file was created.

```bash
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
drwxr-xr-x.  4 xhanti xhanti   71 Aug 24 13:34 RedHat-Enterprise-Linux-
drwx------.  2 xhanti xhanti   88 Aug 24 13:34 .ssh
drwxr-xr-x.  2 xhanti xhanti    6 Aug 18 13:39 Templates
-rw-r--r--.  1 xhanti xhanti    0 Aug 24 14:37 test
drwxr-xr-x.  2 xhanti xhanti    6 Aug 18 13:39 Videos
```

> **Note:** `mv` is used to move or rename files and directories. It does not copy files.

```bash
# Move the test file into the Documents directory.
[xhanti@localhost ~]$ mv test Documents/
```

If we list the `Documents` directory, we can see the `test` file inside it.

```bash
[xhanti@localhost ~]$ ls Documents/
test
```

We can then change into the directory to work with the file.

```bash
[xhanti@localhost ~]$ cd Documents/
```

We can also use `mv` to rename files.

```bash
# Rename test to test.txt
[xhanti@localhost Documents]$ mv test test.txt
[xhanti@localhost Documents]$ ls
test.txt
```

We can use `echo` to create a file and add content to it in a single command.

```bash
[xhanti@localhost ~]$ echo "This is an example, smile :)" > test-smile.txt
```

We can verify that the file was created:

```bash
[xhanti@localhost ~]$ ls -lha
```

```text
# There's our test-smile file :)
-rw-r--r--. 1 xhanti xhanti 29 Aug 24 14:51 test-smile.txt
```

### Copying Files

`cp` is used to copy files and directories.

```bash
# Copy the file to Documents.
[xhanti@localhost ~]$ cp test-smile.txt Documents/
[xhanti@localhost ~]$ ls Documents/
test-smile.txt  test.txt
```

We can use `cat` to display the contents of a file.

```bash
[xhanti@localhost ~]$ cat Documents/test-smile.txt
This is an example, smile :)
```

---

> [!WARNING]
> **Destructive Commands**
>
> Commands such as `rm` permanently remove files and directories. Be careful when using them, especially with elevated privileges such as `sudo`.

```bash
[xhanti@localhost ~]$ ls
Desktop    Music     RedHat-Enterprise-Linux-  Videos
Documents  Pictures  Templates                 wazuh-install-files.tar
Downloads  Public    test-smile.txt            wazuh-install.sh
```

Use `rm` to remove files.

```bash
[xhanti@localhost ~]$ rm test-smile.txt
```

We can create a directory using `mkdir`:

```bash
[xhanti@localhost ~]$ mkdir -p foo
```

We can then remove the directory using `rm -r`.

```bash
[xhanti@localhost ~]$ rm -r foo/
```

The `-r` option tells `rm` to recursively remove a directory and its contents.

If you want to reduce the risk of accidentally removing files, you can use the `-i` option. This makes `rm` ask for confirmation before removing files or directories.

```bash
[xhanti@localhost ~]$ rm -ri Documents/
rm: descend into directory 'Documents/'? no
```

---

> `cd` → **Change directory**. This command is used to move from one directory to another and can take a directory path as an argument.
>
> **Synopsis:** `cd [-L | -P] [dir]`

```bash
# Shell output
[xhanti@localhost ~]$ cd Downloads/
[xhanti@localhost Downloads]$
```

---

### Learning Takeaway

```text
ls, cd, rm, touch, mkdir, cp, and mv are some of the most commonly used
commands in Linux and are essential for managing files and directories
from the shell.
```
