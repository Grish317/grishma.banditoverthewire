# Bandit Level 5 → Level 6

## Level Goal

The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable

## Commands you may need to solve this level

[ls](https://man7.org/linux/man-pages/man1/ls.1.html) , [cd](https://man7.org/linux/man-pages/man1/cd.1p.html) , [cat](https://man7.org/linux/man-pages/man1/cat.1.html) , [file](https://man7.org/linux/man-pages/man1/file.1.html) , [du](https://man7.org/linux/man-pages/man1/du.1.html) , [find](https://man7.org/linux/man-pages/man1/find.1.html)

### Solution:

From the previous level, we have the password:

**Password:** 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

To SSH into the server, use the following command:

**Command:**

ssh [bandit5@bandit.labs.overthewire.org](mailto:bandit1@bandit.labs.overthewire.org) -p 2220

enter the password: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd inhere
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere04  maybehere08  maybehere12  maybehere16
maybehere01  maybehere05  maybehere09  maybehere13  maybehere17
maybehere02  maybehere06  maybehere10  maybehere14  maybehere18
maybehere03  maybehere07  maybehere11  maybehere15  maybehere19
bandit5@bandit:~/inhere$ find . -type f -size 1033c ! -executable
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

### Command Explanation:

1. **`find`**: This is the command used to search for files and directories within a directory hierarchy.
2. **`.`**: Represents the current directory. So, `find .` means we're starting the search from the current directory.
3. **`type f`**: Specifies that we are interested in regular files (not directories or other types of files).
4. **`size 1033c`**: Finds files that are exactly 1033 bytes in size. Here, `c` indicates bytes. You can also use `k` for kilobytes or `M` for megabytes.
5. **`! -executable`**: Excludes files that are executable. The `!` (not) operator negates the condition. `executable` checks if a file has executable permissions.