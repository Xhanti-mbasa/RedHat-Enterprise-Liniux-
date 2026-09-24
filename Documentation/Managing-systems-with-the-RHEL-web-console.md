# Managing Systems with the RHEL Web Console

Not every RHEL administration task has to be performed from the command line. RHEL includes a web-based graphical management interface known as the **RHEL web console**, which is based on the upstream **Cockpit** project.

The web console can be used to manage and monitor a local system or Linux servers on the network.

Depending on the installed components, we can use it for tasks such as:

* Managing services.
* Managing user accounts.
* Configuring networking and the firewall.
* Reviewing system logs.
* Managing storage.
* Updating software.
* Viewing system performance and health information.

The web console uses the same underlying system tools as the command line. A change made in the terminal is reflected in the web console, and a change made in the web console changes the same system configuration.

### Enabling the Web Console

If Cockpit is not installed, it can be installed with DNF:

```bash
sudo dnf install cockpit
```

We can enable and start its socket with:

```bash
sudo systemctl enable --now cockpit.socket
```

The web console normally listens on port `9090`. On the local machine, we can open:

```text
https://localhost:9090
```

and log in using a system user account.

### Learning Takeaway

```text
The RHEL web console provides a graphical way to perform many common system
administration tasks. It does not replace the command line; both interfaces
manage the same underlying RHEL system and can be used together.
```
