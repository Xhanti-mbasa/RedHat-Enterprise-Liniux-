# Managing Software and Updates

Software on Red Hat Enterprise Linux is normally distributed as **RPM packages**. RHEL uses **DNF** to install, update, remove, and query software from configured repositories.

A repository is a collection of software packages and package metadata that DNF can use.

We can search for a package with:

```bash
dnf search <package>
```

To view information about a package:

```bash
dnf info <package>
```

To install software, administrative privileges are normally required:

```bash
sudo dnf install <package>
```

For example:

```bash
sudo dnf install httpd
```

DNF resolves dependencies for us. If the package requires other packages, DNF can install the required dependencies as part of the transaction.

### Updating Software

We can check for available updates with:

```bash
dnf check-update
```

To update installed packages:

```bash
sudo dnf upgrade
```

DNF shows the transaction before making changes and normally asks us to confirm it.

### Removing Software

We can remove an installed package with:

```bash
sudo dnf remove <package>
```

### RPM

The lower-level `rpm` command can query the RPM package database directly.

For example, to list installed packages:

```bash
rpm -qa
```

To query a specific installed package:

```bash
rpm -q bash
```

DNF is normally preferred for installing and removing software because it understands repositories and handles dependencies.

### Learning Takeaway

```text
RHEL software is distributed using RPM packages, while DNF is the main tool
used to work with packages and repositories. DNF can search, install, update,
and remove software while automatically handling package dependencies.
```
