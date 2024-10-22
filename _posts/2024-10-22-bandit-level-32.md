# Bandit Level 32 → Level 33

## Level Goal

After all this `git` stuff, it’s time for another escape. Good luck!

## Commands you may need to solve this level

sh, man

### Solution:

From the previous level, we have the password:

**Password:** 3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K

To SSH into the server, use the following command:

**Command:**

ssh [bandit32@bandit.labs.overthewire.org](mailto:bandit1@bandit.labs.overthewire.org) -p 2220

enter the password: 3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K

WELCOME TO THE UPPERCASE SHELL

Tried various stuff, at last the uppershell can be removed by using @$0

> $0
$ ls -al
total 36
drwxr-xr-x  2 root     root      4096 Jul 17 15:57 .
drwxr-xr-x 70 root     root      4096 Jul 17 15:58 ..
-rw-r--r--  1 root     root       220 Mar 31 08:41 .bash_logout
-rw-r--r--  1 root     root      3771 Mar 31 08:41 .bashrc
-rw-r--r--  1 root     root       807 Mar 31 08:41 .profile
-rwsr-x---  1 bandit33 bandit32 15136 Jul 17 15:57 uppershell
$ cat /etc/bandit_pass/bandit33
tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0
$
>