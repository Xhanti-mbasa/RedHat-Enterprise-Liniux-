# Documentation

Linux comes with built in documentation for commands, configuration files, system calls, and other parts of the operating system. This documentation is available online and directly from the command line through **manual pages**, commonly referred to as **man pages**.

You can access this documentation directly from your shell whenever you need help with a command or configuration file.

For example, if I wanted to learn how to compress and uncompress files and directories, I could type:

```bash
man tar
```

Instead of leaving the shell and searching Google, I can use the documentation already available on my system. This means you don't need to memorize every command or remember every option.

If you need information about a configuration file, you can specify the relevant **manual section**. For example:

```bash
man 5 crontab
```

The `5` specifies that you want the manual page from section 5, which contains information about **file formats and configuration files**.

You can even use:

```bash
man man
```

to learn about `man` itself, including how manual pages are structured and how to navigate them.

### Learning Takeaway

```text
You don't have to memorize every command or know exactly what every command
does. You can always refer to the manual, also known as the man pages, whenever
you need clarification about a command, option, configuration file, or other
part of the Linux system.
```
