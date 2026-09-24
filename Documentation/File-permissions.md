# File Permissions

Linux file permissions control who can read, change, or execute files and directories. Permissions are divided between the **user**, **group**, and **others**.

We can view permissions using:

```bash
ls -l
```

Example:

```text
-rwxr-xr--. 1 xhanti developers 120 Sep 24 12:00 script.sh
```

The first character tells us the file type. A `-` represents a regular file, while `d` represents a directory.

The next nine characters are split into three groups:

```text
rwx r-x r--
│   │   └── others
│   └────── group
└────────── user/owner
```

The permission letters mean:

* `r` → **read**
* `w` → **write**
* `x` → **execute**
* `-` → that permission is not granted

For the example above, the owner can read, write, and execute the file. Members of the file's group can read and execute it. Everyone else can only read it.

### Changing Permissions

We can use `chmod` to change file permissions.

```bash
chmod u+x script.sh
```

* `u` → User/owner.
* `+` → Add a permission.
* `x` → Execute permission.

We can also remove a permission:

```bash
chmod o-r script.sh
```

Or assign permissions using numeric values:

```bash
chmod 750 script.sh
```

The numeric values are based on:

```text
read    = 4
write   = 2
execute = 1
```

So `750` means:

```text
7 = rwx
5 = r-x
0 = ---
```

### Ownership

Every file has an owner and a group. We can change them using `chown`.

```bash
sudo chown alice:developers example.txt
```

This changes the owner to `alice` and the group to `developers`.

> **Note:** Directory permissions have slightly different effects from regular files. For a directory, execute permission allows a user to access entries inside it, while read permission allows the directory contents to be listed.

### Learning Takeaway

```text
Linux permissions are read from left to right as user, group, and others.
The r, w, and x permissions control reading, writing, and execution, while
chmod and chown are used to change permissions and ownership.
```
