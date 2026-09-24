# Managing Networking

A Linux system needs networking information such as an IP address, a route to other networks, and DNS servers before it can communicate normally across a network.

We can inspect network interfaces and IP addresses with:

```bash
ip address
```

A shorter version is:

```bash
ip a
```

To inspect the routing table:

```bash
ip route
```

The default route is the route the system normally uses when traffic is destined for a network that does not have a more specific route.

### NetworkManager

Red Hat Enterprise Linux uses **NetworkManager** to manage network connections. From the command line, we can interact with NetworkManager using `nmcli`.

To view devices:

```bash
nmcli device status
```

To view configured connections:

```bash
nmcli connection show
```

We can display information about a specific connection with:

```bash
nmcli connection show <connection-name>
```

Network settings can be supplied automatically by **DHCP**, or configured manually when a system needs a static address.

### Testing Connectivity

We can test whether another host is reachable with:

```bash
ping <hostname-or-ip>
```

For example:

```bash
ping -c 4 8.8.8.8
```

The `-c 4` option tells `ping` to send four requests and then stop.

If communication by IP address works but communication by hostname does not, DNS configuration is one of the things we should investigate.

### Learning Takeaway

```text
Networking requires an address, routes, and usually DNS. The ip command is
useful for inspecting the current network state, while NetworkManager and
nmcli are used to manage network connections on RHEL.
```
