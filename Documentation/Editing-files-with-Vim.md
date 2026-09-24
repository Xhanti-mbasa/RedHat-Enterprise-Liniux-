# Editing Files with Vim

Vim is a text editor that can be used directly from the terminal. This makes it especially useful for system administrators because you can edit configuration files even when a graphical desktop is not available.

To open a file in Vim, we can use:

```bash
vim example.txt
```

Vim works using different **modes**. When Vim first opens, we are normally in **Normal mode**. Normal mode is used to move around the file and issue commands.

To start typing text, press:

```text
i
```

This puts Vim into **Insert mode**. In Insert mode, we can type and edit text normally.

To leave Insert mode and return to Normal mode, press:

```text
Esc
```

### Saving and Exiting

Once we're back in Normal mode, we can save the file with:

```text
:w
```

* `:` → Starts a command in Vim.
* `w` → Write the changes to the file.

To quit Vim:

```text
:q
```

We can combine the two commands to save and quit:

```text
:wq
```

If we want to quit without saving our changes, we can use:

```text
:q!
```

The `!` tells Vim to force the operation.

> **Note:** Vim can do significantly more than the commands shown here. For basic system administration, the important part is being able to open a file, enter Insert mode, make a change, save it, and exit the editor.

### Learning Takeaway

```text
Vim is useful because it works directly in the terminal. Remember the basic flow:
open the file, press i to enter Insert mode, press Esc to return to Normal mode,
and use :wq to save and exit.
```
