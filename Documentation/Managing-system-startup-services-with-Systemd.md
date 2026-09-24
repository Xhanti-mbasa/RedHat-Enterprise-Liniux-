# Managing System Startup Services with Systemd

When Linux boots, many background programs need to be started and managed. Red Hat Enterprise Linux uses **systemd** as its system and service manager.

A background service managed by systemd is represented by a **unit**. Service units normally end in `.service`.

We interact with systemd using `systemctl`.

To see the status of a service:

```bash
systemctl status sshd
```

To start a service now:

```bash
sudo systemctl start sshd
```

To stop it:

```bash
sudo systemctl stop sshd
```

To restart a service:

```bash
sudo systemctl restart sshd
```

### Starting Services at Boot

Starting a service and enabling a service are not the same thing.

```bash
sudo systemctl enable sshd
```

`enable` configures the service to start automatically at the appropriate point during future boots.

We can disable that behavior with:

```bash
sudo systemctl disable sshd
```

If we want to enable a service and start it immediately, we can use:

```bash
sudo systemctl enable --now sshd
```

### Systemd Targets

Systemd also uses **targets** to group units together and represent useful system states. Targets replace the traditional idea of SysV init runlevels on modern RHEL systems.

We can see the default target with:

```bash
systemctl get-default
```

### Learning Takeaway

```text
Systemd manages services and other units on RHEL. systemctl can inspect,
start, stop, restart, enable, and disable services. Starting controls the
current state, while enabling controls whether a service starts at boot.
```
