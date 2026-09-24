# Organizing Local Users and Groups

Linux is a multi-user operating system. Different people and services can have their own user accounts, and users can be organized into groups to make permissions easier to manage.

We can see information about our current user with:

```bash
id
```

The output includes our **UID** (user ID), our primary **GID** (group ID), and the groups that the user belongs to.

```bash
[xhanti@localhost ~]$ id
uid=1000(xhanti) gid=1000(xhanti) groups=1000(xhanti),10(wheel)
```

Linux identifies users and groups internally using these numeric IDs, even though we normally work with their names.

### The Root User

The `root` user is the system's superuser. Root has administrative access to the system and can make changes that a normal user cannot.

Instead of logging in as root for normal work, we can use `sudo` to run an administrative command when needed.

```bash
sudo <command>
```

On RHEL, members of the `wheel` group are commonly allowed to use `sudo` according to the system's sudo configuration.

We can switch to a root login shell with:

```bash
sudo -i
```

> [!WARNING]
> Commands run as root can change or remove important system files. Administrative access should only be used when it is required.

### Creating Users

We can create a local user with `useradd`:

```bash
sudo useradd alice
```

We can then give the user a password:

```bash
sudo passwd alice
```

Local account information is stored in files such as:

```text
/etc/passwd
/etc/group
/etc/shadow
```

`/etc/passwd` contains basic account information, `/etc/group` contains group information, and password hashes are stored separately in `/etc/shadow`, which is protected from normal users.

### Groups

Groups allow us to give several users access to the same files or resources without configuring each user separately.

We can create a group with:

```bash
sudo groupadd developers
```

Then add an existing user to the group:

```bash
sudo usermod -aG developers alice
```

* `-a` → Append the user to the supplementary group list.
* `-G` → Specify supplementary groups.

We can verify the user's group membership with:

```bash
id alice
```

### Learning Takeaway

```text
Linux uses users and groups to identify who is using the system and what they
should be allowed to access. Administrative work is performed with root
privileges, while groups make it easier to manage access for multiple users.
```
