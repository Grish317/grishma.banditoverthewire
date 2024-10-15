# Bandit Level 17 → Level 18

## Level Goal

There are 2 files in the homedirectory: **passwords.old and passwords.new**. The password for the next level is in **passwords.new** and is the only line that has been changed between **passwords.old and passwords.new**

**NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19**

## Commands you may need to solve this level

cat, grep, ls, diff

Solution:

bandit17@bandit:~$ ls -al
total 36
drwxr-xr-x  3 root     root     4096 Jun 20 04:06 .
drwxr-xr-x 70 root     root     4096 Jun 20 04:08 ..
-rw-r-----  1 bandit17 bandit17   33 Jun 20 04:06 .bandit16.password
-rw-r--r--  1 root     root      220 Mar 31 08:41 .bash_logout
-rw-r--r--  1 root     root     3771 Mar 31 08:41 .bashrc
-rw-r-----  1 bandit18 bandit17 3300 Jun 20 04:06 passwords.new
-rw-r-----  1 bandit18 bandit17 3300 Jun 20 04:06 passwords.old
-rw-r--r--  1 root     root      807 Mar 31 08:41 .profile
drwxr-xr-x  2 root     root     4096 Jun 20 04:06 .ssh

bandit17@bandit:~$ diff passwords.new passwords.old
42c42
< x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO

>FtePUTiLiwPzjIFw2T7o57oBS4zUvPpg

The output will show differences between the two files. The lines prefixed with `<` are from `password.new`, and those prefixed with `>` are from `passwords.old`.

The password is x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO since password for the next level is in **passwords.new.**