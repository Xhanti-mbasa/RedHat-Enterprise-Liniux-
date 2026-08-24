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

# List files in a [human readable format](./Introduction-to-the-shell.md#human-readable-format) that's easier to read.
ls -lh 

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
