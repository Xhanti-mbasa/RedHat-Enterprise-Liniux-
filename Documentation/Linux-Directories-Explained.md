# Linux Directories Explained

On Linux, everything starts from the root directory, represented by `/`. From there, everything else branches out.

### To list our directories

To list the directories in the root directory, we use:

```bash
ls /
```

* `ls` → list. This is our command. We can use `man`, which we covered in the previous lesson, [Introduction to the Shell](https://github.com/Xhanti-mbasa/RedHat-Enterprise-Liniux-/blob/main/Documentation/Introduction-to-the-shell.md).
* `/` → The forward slash represents the root directory and is our argument.

<img width="1356" height="755" alt="image" src="https://github.com/user-attachments/assets/133061a7-cd5a-46f0-8f92-b9bdd10d222c" />

### To change directories

To change directories, we use:

```bash
cd usr
```

* `cd` → Change directory. This is our command.
* `<path/>` → Our path/directory. This can be any directory we wish to `cd` into and is our argument.

<img width="1356" height="755" alt="image" src="https://github.com/user-attachments/assets/74cb0171-a334-44ca-b6e1-2039308b0e20" />

`usr` contains user-related programs, libraries, and shared resources. It is not specifically where all users on the system are stored.

### etc

* `/etc` contains system-wide configuration files. If you're changing the configuration of your system, this is likely where you'll make some of those changes.
* As a common practice, you should back up important configuration files before making changes.

### var

* `/var` is where variable data is stored, such as logs. These are files and data that change frequently on your system.

### usr

* `/usr` is where many user-space programs and resources are stored.
* `/usr/bin` contains many executable programs (binaries).
* `/usr/lib` contains libraries used by programs.
* `/usr/share` contains architecture-independent shared resources, such as documentation and other data.

### tmp

* `/tmp` is where the system stores temporary files and where users can save temporary data.
* Because temporary files may be accessible to other users or automatically deleted, **don't store sensitive information here**.

### /

* `/` is the root directory of the entire Linux filesystem.
* The **root user** (superuser) is different from the root directory. The root user typically has unrestricted administrative privileges.

### boot

* `/boot` contains the files required for the system to boot, such as the Linux kernel and bootloader-related files.
* Unless you're troubleshooting boot-related issues, you won't normally need to work in this directory.

### mnt

* `/mnt` is commonly used as a temporary mount point for filesystems, such as USB drives or additional hard drives.

### run

* `/run` contains runtime data for currently running processes and services.
* Its contents are generally created when the system boots and can change while the system is running.

### Learning Takeaway

> **Everything in Linux is treated as a file, and the entire system can be interacted with through these files. Understanding the Linux filesystem structure is therefore important when learning how to work with Linux.**
