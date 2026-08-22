# Command Line Assistant

Red Hat provides a built in command line assistant that can help you work with your RHEL system directly from the terminal. Your system needs to be registered with Red Hat before you can use the assistant.

To use the assistant, you can run:

```bash
c chat "prompt"
```

The RHEL assistant will then process the prompt and provide a response directly in the terminal.

You can register your RHEL system using **Red Hat Subscription Manager** directly from the shell. Alternatively, if your organization operates a **Satellite Server**, you can register your system with the Satellite Server instead.

Red Hat Satellite can act as a centralized management platform for RHEL systems, allowing organizations to manage software, updates, configurations, and subscriptions from a controlled internal environment. It can also provide local software repositories, reducing the need for every system to retrieve packages directly from Red Hat.
