---
description: >-
  More advanced bash concepts like piping, aliases, and more explained in one
  guide, that will help you save time and energy.
---

# Bash - Do More With Less

{% hint style="info" %}
This content is from an upcoming [Raspberry Pi hosting course](../raspberry-pi-hosting/overview.md).
{% endhint %}

## Wildcards

Wildcard characters are used to define **patterns** for searching text on data in bash.

### Star or Asterisk \(\*\)



### Question Mark \(?\)

### Square Brackets \(\[\]\)

## Piping

### What is a pipeline?

In computer science, a pipeline is a **series** of **elements**, where each one is **connected** to the **next**.

![](../.gitbook/assets/image%20%2826%29.png)

### The Command Pipeline

```bash
$ echo "Hello Earth"
Hello Earth
```

**\[0\] Standard Input** - typed command and its arguments; stdin.  
**\[1\] Standard Output** - normal output from a command; stdout.  
**\[2\] Standard Error** - error output from a command; stderr.

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

## Brace Expansion

Brace expansion is used to generate strings.

{% tabs %}
{% tab title="Combinations" %}
```bash
$ echo {a..z}
a b c d e f g h i j k l m n o p q r s t u v w x y z
$ echo {z..w}
z y x w
$ echo {1..10}
1 2 3 4 5 6 7 8 9 10
$ echo {3..-1}
3 2 1 0 -1
```
{% endtab %}

{% tab title="Prefix/Suffix" %}
```bash
$ echo a{a..f}
aa ab ac ad ae af
$ echo {1..3} && echo {99,100}
1 2 3 99 100
```
{% endtab %}

{% tab title="List Command Example" %}
```bash
$ ls {Desktop,Documents}
Desktop:
'Visual Studio Code.lnk'*   desktop.ini

Documents:
'My Music'@  'My Pictures'@  'My Videos'@   desktop.ini
```
{% endtab %}
{% endtabs %}

### Nested Brace Expansion

```bash
$ echo {a,{a..c},{a..c}}
a a b c a b c
```

{% hint style="warning" %}
Make sure there are no spaces around commas, otherwise brace expansion will not work.
{% endhint %}

### Multiple Brace Expansion

_Brace_ yourself for a basic maths lesson.

$$
3^2=3*3=9
$$

```bash
$ echo {1..3} # 3*1 = 3 combinations
1 2 3
$ echo {1..3}{1..3} # 3*3 = 9 combinations
11 12 13 21 22 23 31 32 33
$ echo {1..3}{1..3}{1..3} # 3*3*3 = 27 combinations
111 112 113 121 122 123 131 132 133 211 212 213 221 222 223 231 232 233 311 312 313 321 322 323 331 332 333
```

## [Challenge - Make a Today Command](../raspberry-pi-hosting/challenges/#challenge-make-a-trash-command)

{% hint style="success" %}
Doing is the most effective way of learning, and will help reinforce your knowledge and understanding.
{% endhint %}

### References

{% hint style="info" %}
This content is from an upcoming [Raspberry Pi hosting course](../raspberry-pi-hosting/overview.md).
{% endhint %}

