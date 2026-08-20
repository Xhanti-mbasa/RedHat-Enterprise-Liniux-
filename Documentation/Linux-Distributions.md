# Linux Distributions

* A distribution is a complete operating system, also known as a (distro) for short, built around the Linux kernel.
* What sets distributions apart are the options and features vendors like Red Hat choose to add or remove to create their own flavor of Linux.
* Red Hat operates three distinct Linux distributions:

  * **Fedora Linux** — The experimental distribution, bringing the latest community projects and technologies.
  * **CentOS Stream** — The middle stream, offering a rolling release preview of features coming to RHEL. It is more stable than Fedora while being more adventurous than RHEL.
  * **Red Hat Enterprise Linux (RHEL)** — The most stable and supported distribution in the lineup, focused on production readiness, support, and a flexible foundation for critical workloads and applications. As the name implies, it is the enterprise option.

Regardless of which option you use, all three share the same RPM package format and use the DNF package manager. A package manager is an important part of a distro because it allows you to download, install, update, and remove packages on your machine.

The packages available through DNF are largely open source, meaning their source code can be viewed, modified, and contributed to. Red Hat doesn't just consume these technologies; it also contributes significantly to the Linux ecosystem through projects and technologies such as **KVM** and **systemd**. Personally, systemd is one of the biggest ones for me because it is my init system of choice on my daily machine. Both technologies originated from Red Hat's ecosystem and have since made their way into many other distributions, including independent distributions such as Arch Linux.

Linux distributions generally share the same core Linux tools, programming languages, databases, and web servers. It is largely the configuration and selection of components that sets them apart. As a consequence, some distributions may use different filesystem standards. Red Hat follows the **Filesystem Hierarchy Standard (FHS)**, which ensures that directories such as `/var` and `/etc` are located where you would expect them to be.

RHEL isn't just for enterprise customers; anyone can get it for free under Red Hat's available subscription options.

RHEL follows a lifecycle with major releases typically supported for many years. Red Hat also provides tools such as **Leapp**, which can be used to perform supported upgrades between major RHEL versions.

RHEL support is divided into several phases. **Full Support** provides bug fixes, new features, and security updates. **Maintenance Support** focuses primarily on security and critical bug fixes. After these phases, **Extended Life Cycle Support (ELS)** may be available as an additional offering, providing selected security and maintenance updates beyond the standard lifecycle.

## Learning Takeaway

```text
If you're looking for a stable and secure Linux distribution with a robust
structure and a reliable support and release cycle, Red Hat distributions
are a great option, especially RHEL.
```
