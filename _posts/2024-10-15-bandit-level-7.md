# Bandit Level 6 → Level 7

## Level Goal

The password for the next level is stored **somewhere on the server** and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

## Commands you may need to solve this level

[ls](https://man7.org/linux/man-pages/man1/ls.1.html) , [cd](https://man7.org/linux/man-pages/man1/cd.1p.html) , [cat](https://man7.org/linux/man-pages/man1/cat.1.html) , [file](https://man7.org/linux/man-pages/man1/file.1.html) , [du](https://man7.org/linux/man-pages/man1/du.1.html) , [find](https://man7.org/linux/man-pages/man1/find.1.html) , [grep](https://man7.org/linux/man-pages/man1/grep.1.html)

### Solution:

From the previous level, we have the password:

**Password:** HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

To SSH into the server, use the following command:

**Command:**

ssh [bandit6@bandit.labs.overthewire.org](mailto:bandit1@bandit.labs.overthewire.org) -p 2220

enter the password: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

bandit6@bandit:~$ ls
bandit6@bandit:~$ ls -a
.  ..  .bash_logout  .bashrc  .profile
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

### Command Explanation:

1. **`find /`**: Starts the `find` command to search from the root directory `/` downwards in the directory hierarchy.
2. **`user bandit7`**: Specifies that the files must be owned by the user `bandit7`.
3. **`group bandit6`**: Specifies that the files must belong to the group `bandit6`.
4. **`size 33c`**: Specifies that the files must be exactly 33 bytes in size. Here, `c` indicates bytes.
5. **`2>/dev/null`**: Redirects standard error (stderr) output to `/dev/null`, suppressing error messages. This ensures that any error messages generated during the search (such as permission denied errors) are not displayed on the terminal.