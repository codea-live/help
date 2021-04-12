---
description: Get started with bash and learn maximize your efficiency with Linux!
---

# Bash Basics

{% hint style="info" %}
From an upcoming Raspberry Pi hosting course \(insert link here\).
{% endhint %}

## How the Terminal Works

The terminal, or command line interface \(CLI\), is a **program** that accepts **text** **input** to **execute** **functions**.

![](../.gitbook/assets/image%20%2822%29.png)

## Pipes - Do More With Less

### What is a pipeline?

In computer science, a pipeline is a **series** of **elements**, where each one is **connected** to the **next**.

![](../.gitbook/assets/image%20%2812%29.png)

### The Command Pipeline

```bash
$ echo "Hello Earth"
Hello Earth
```

**\[0\] Standard Input** - typed command and its arguments.  
**\[1\] Standard Output** - normal output from a command.  
**\[2\] Standard Error** - error output from a command.

![](../.gitbook/assets/image%20%2820%29.png)

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

