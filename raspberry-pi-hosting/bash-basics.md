---
description: Get started with bash and learn maximize your efficiency with Linux!
---

# Bash Basics

{% hint style="info" %}
From an upcoming Raspberry Pi hosting course \(insert link here\).
{% endhint %}

## How the Terminal Works

### What is the terminal?

The terminal, or command line interface \(CLI\), is a **program** that accepts **text** **input** to **execute** **functions**.

![](../.gitbook/assets/image%20%2842%29.png)

### What is a command?

A command is **text** in a **command** **line** that **executes** a **program**.  
Commands are simply programs.

`echo “Hello World”` is equal to `/usr/bin/echo “Hello World”`

![](../.gitbook/assets/image%20%2812%29.png)

### Command Anatomy - Prefix

![](../.gitbook/assets/image%20%2827%29.png)

### Command Anatomy - Command

![](../.gitbook/assets/image%20%2832%29.png)

### What is the PATH?

The PATH stores **where** commands are located - more specifically, all directories where they are found. This makes it easy for bash to find commands to be found by name, as it knows where to look.

```bash
$ echo $PATH
/usr/bin/node/bin:/home/adam/.local/bin:/home/adam/bin:/usr/bin/node/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
```

{% hint style="info" %}
You may get different output, with different operating systems. Ubuntu 20.04 was used for this demo.
{% endhint %}

## man - The Command Manual

The **man**ual lets you find all you need to know about a _most_ commands.

### Syntax

```bash
$ man <command_name>
```

> "man is the system's manual pager. Each page argument given to man is normally the name of a program, utility or function. The manual page associated with each of these arguments is then found and displayed. A section, if provided, will direct man to look only in that section of the manual. The default action is to search in all of the avail‐ able sections following a pre-defined order \(see DEFAULTS\), and to show only the first page found, even if page exists in several sections."

— Manual page on the man command.

### What if the manual does not cover it?

The **help** command is available for some default bash commands.  
For example, **cd** does not have a manual page, and details info can be found with it.

```bash
$ help <command_name>
```



## Pipes - Do More With Less

### What is a pipeline?

In computer science, a pipeline is a **series** of **elements**, where each one is **connected** to the **next**.

![](../.gitbook/assets/image%20%2826%29.png)

### The Command Pipeline

```bash
$ echo "Hello Earth"
Hello Earth
```

**\[0\] Standard Input** - typed command and its arguments.  
**\[1\] Standard Output** - normal output from a command.  
**\[2\] Standard Error** - error output from a command.

![](../.gitbook/assets/image%20%2828%29.png)

### We Can Control Command Output

```bash
$ echo "Hello Earth" 0>> echo
$ Hello Earth
```

This command puts the output of the first command into the second command.

```bash
$ echo "Hello Earth" 1>> output.txt
$ cat output.txt
Hello Earth
```

This puts the output of the first command into a file \(output.txt\).

```bash
$ cat '' 2>> error.txt
$ cat error.txt
cat: '': No such file or directory
```

This puts the error from the cat command, into a file \(error.txt\).

### Logical Operators Can Help Too

Logical operators are used for command pipelines.

```bash
A ; B     # Run A and then B, regardless of success of A
A && B    # Run B if A succeeded
A || B    # Run B if A failed
A &       # Run A in background.
```

{% embed url="https://unix.stackexchange.com/questions/24684/confusing-use-of-and-operators" caption="More on Logical Operators" %}

