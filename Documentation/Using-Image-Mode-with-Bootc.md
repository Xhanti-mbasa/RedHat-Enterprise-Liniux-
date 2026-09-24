# Using Image Mode with Bootc

RHEL Image Mode provides a different way to manage the operating system. Instead of treating the machine as a collection of individually managed packages, the operating system can be built, distributed, and updated as a **bootable container image**.

The tool used to work with these bootable container systems is `bootc`.

A normal application container contains an application and its dependencies. A bootable container image goes further and contains the operating-system content needed to create or update a host.

This gives us a workflow that looks more like working with container images:

```text
Build image → Store image in a registry → Deploy image → Update from a new image
```

Because the operating system is represented as an image, the same image can be tested before it is deployed to multiple systems. This can make deployments more repeatable because systems can be moved toward the same known operating-system state.

We can inspect the bootc state of an Image Mode system with:

```bash
bootc status
```

Updates can be staged from a newer image and applied through the boot process. Image Mode also keeps deployment information that can make it possible to return to an earlier deployment when required.

> **Note:** Image Mode does not mean that the machine only runs containers. It changes how the host operating system itself is built, delivered, and updated.

### Learning Takeaway

```text
RHEL Image Mode treats the operating system as a bootable container image.
Bootc provides the tools used to deploy and update that image-based system,
which makes the operating-system state easier to reproduce and manage.
```
