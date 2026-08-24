# Introduction to the Shell

The shell is one of the most powerful tools in Linux, allowing you to interact with and make changes to your system. The default shell on many Linux distributions is **Bash**.

The basic structure of a command in the shell consists of a **command**, **options**, and **arguments**.

Options can start with a single dash (`-`) or two dashes (`--`) and, as the name suggests, are usually optional. Some commands, such as `ls`, can run without any options.

Commands can also have arguments. For example:

```bash
ls -a Documents/
```

* `ls` → The command.
* `-a` → An option using a single dash. This tells `ls` to show hidden files.
* `Documents/` → The argument, which tells `ls` what directory to operate on.

Options influence how a command behaves, while arguments specify the files, directories, or other resources you want the command to operate on. When referring to a directory, a trailing forward slash (`/`) can be used to make it explicit that the path refers to a directory.

In this example, we're checking how much space our home directory is using:

```bash
du -sh /home/xhanti-rhel/
```

* `du` → The command used to estimate file space usage.
* `-sh` → Two options combined together:

  * `-s` → Summarize the result instead of displaying usage for every subdirectory.
  * `-h` → <span id="human-readable-format">Display the output in a human readable format.</span>
* `/home/xhanti-rhel/` → The argument specifying the directory we want to check.

The first forward slash in `/home/xhanti-rhel/` represents the root directory. From there, the path goes into the `home` directory and then into the `xhanti-rhel` user's home directory.

We can use:

```bash
pwd
```

to see which directory we're currently in.

By default, when we open a new interactive shell, we normally start in our user's home directory, not the `/usr` directory. Another name for a directory is a **folder**.

### Output

```bash
xhanti-rhel@localhost:~$ du -sh /home/xhanti-rhel/
466M    /home/xhanti-rhel/
```

## Tab Completion

We can use the **TAB** key on our keyboard to make writing commands faster. TAB completion allows the shell to automatically complete commands, filenames, directories, and other arguments when enough context has been provided.

For example, suppose we want to change directories from:

```text
/home/xhanti-rhel/
```

to:

```text
/home/xhanti-rhel/Documents/
```

If all we type is:

```bash
cd
```

there is not enough context to determine what we want to complete. Depending on the shell and its configuration, pressing TAB may cause it to display possible command completions, such as:

```text
xhanti-rhel@localhost:~$ cd
cd                 cd-drive           cd-info
cd-create-profile  cd-fix-profile     cd-it8
cdda-player        cd-iccdump         cd-read
```

Instead, if we provide a space after `cd`, we are telling the shell that we want to provide an argument to the `cd` command:

```bash
cd <TAB>
```

The shell can then show us directories available in our current location:

```text
xhanti-rhel@localhost:~$ cd
.cache/    Desktop/   Downloads/ .mozilla/  Pictures/  .ssh/      tmp2/      Videos/
.config/   Documents/ .local/    Music/     Public/    Templates/ .var/      WTC/
```

Now we can narrow down our selection:

```bash
cd D<TAB>
```

The shell can see that several directories begin with `D`:

```text
Desktop/   Documents/   Downloads/
```

There still isn't enough information to uniquely determine which directory we want.

We can provide more context:

```bash
cd Doc<TAB>
```

Now there is only one matching directory:

```text
Documents/
```

The shell can therefore automatically complete the command for us:

```bash
cd Documents/
```

This is a simple example of how TAB completion can make working in the shell significantly faster.

It's also important to refer to a command's help or manual page to understand which options and arguments are available.

## Learning Takeaway

```text
TAB completion is useful for discovering available commands, files, directories,
and other arguments when enough unique context has been provided. It also saves
time when writing commands and can reduce mistakes caused by manually typing
long commands or paths.
```
