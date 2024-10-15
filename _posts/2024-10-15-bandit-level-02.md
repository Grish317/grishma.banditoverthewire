# Bandit Level 1 → Level 2

## Level Goal

The password for the next level is stored in a file called **-** located in the home directory

## Commands you may need to solve this level

[ls](https://man7.org/linux/man-pages/man1/ls.1.html) , [cd](https://man7.org/linux/man-pages/man1/cd.1p.html) , [cat](https://man7.org/linux/man-pages/man1/cat.1.html) , [file](https://man7.org/linux/man-pages/man1/file.1.html) , [du](https://man7.org/linux/man-pages/man1/du.1.html) , [find](https://man7.org/linux/man-pages/man1/find.1.html)

## Helpful Reading Material

- [Google Search for “dashed filename”](https://www.google.com/search?q=dashed+filename)
- [Advanced Bash-scripting Guide - Chapter 3 - Special Characters](http://tldp.org/LDP/abs/html/special-chars.html)

### Solution:

From the previous level, we have the password:

**Password:** `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If`

To SSH into the server, use the following command:

**Command:**

ssh [bandit1@bandit.labs.overthewire.org](mailto:bandit1@bandit.labs.overthewire.org) -p 2220

enter the password: `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If`

Once logged in, list the files in the directory:

bandit1@bandit:~$ ls

You will see a file named `-`. To view its contents, use one of the following methods:

Method 1: Using `./-` 

bandit1@bandit:~$ cat ./-
263JGJPfgU6LtdEvgfWU1XP5yac29mFx

Method 2: Using `--` to indicate the end of options

bandit1@bandit:~$ cat -- -
263JGJPfgU6LtdEvgfWU1XP5yac29mFx

### Why `` Filename is Not Directly Accessible:

If you try to access a file named `-` using a command like `cat -`, it will be interpreted as standard input rather than a filename. The `-` character is commonly used in command-line utilities to signify standard input or options. This can cause confusion and unintended behavior when accessing such filenames.

To avoid this issue, you can:

- Prefix the filename with `./`, specifying the current directory.
- Use `-` to indicate the end of command options, ensuring subsequent arguments are treated as filenames.

These methods ensure that the `cat` command interprets `-` correctly as a filename and not as an option or standard input.