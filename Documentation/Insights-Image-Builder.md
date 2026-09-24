# Insights Image Builder

Red Hat provides an image-building service that can be used to create customized RHEL system images. Instead of manually installing and configuring every machine from the beginning, we can define the image we need and build a reusable system image.

The image can include choices such as the RHEL release, system architecture, packages, and other configuration needed for the target environment.

A typical workflow is:

```text
Choose image settings → Add packages/configuration → Build image → Download or deploy image
```

Different environments need different image formats. For example, a system being installed on physical or virtual infrastructure may need a different output format from a system being deployed to a cloud provider.

Using an image builder makes deployments more consistent because we can start multiple systems from the same defined image rather than repeating the installation manually on every host.

The image-building capabilities are integrated with Red Hat's management services, allowing administrators to build RHEL images through a web-based workflow.

### Learning Takeaway

```text
Image Builder allows us to create customized and repeatable RHEL images for
our target environment. Instead of configuring every machine from scratch,
we can define the desired image once and use it as the starting point for
new systems.
```
