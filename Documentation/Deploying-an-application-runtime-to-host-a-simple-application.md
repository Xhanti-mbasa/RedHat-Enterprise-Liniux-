# Deploying an Application Runtime to Host a Simple Application

Applications need a runtime environment containing the software and dependencies required to run them. On RHEL, we can install an application runtime using the normal package management tools and then use it to host an application.

For example, if an application requires a particular runtime, we can search the available software using DNF:

```bash
dnf search <runtime>
```

We can then install the required package:

```bash
sudo dnf install <runtime-package>
```

Once the runtime is installed, the application can be placed on the system and started using the runtime that it expects.

This is an important distinction:

```text
Application → the code we want to run
Runtime     → the environment/software required to run that code
```

RHEL provides supported software through its repositories, which allows runtimes and their dependencies to be installed and updated using the same package-management workflow as other system software.

When an application is intended to run continuously, we can also manage it as a service so that systemd can control when it starts, stops, and whether it should start during boot.

### Learning Takeaway

```text
Before an application can run, the system needs the runtime and dependencies
that the application expects. On RHEL, those components can be installed and
maintained through the operating system's software-management tools.
```
