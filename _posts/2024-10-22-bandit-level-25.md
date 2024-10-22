# Bandit Level 25 → Level 26

## Level Goal

Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not **/bin/bash**, but something else. Find out what it is, how it works and how to break out of it.

## Commands you may need to solve this level

ssh, cat, more, vi, ls, id, pwd

### Solution:

From the previous level, we have the password:

**Password:** iCi86ttT4KSNe1armKiwbQNmB3YJP3q4

To SSH into the server, use the following command:

**Command:**

ssh [bandit25@bandit.labs.overthewire.org](mailto:bandit1@bandit.labs.overthewire.org) -p 2220

enter the password: iCi86ttT4KSNe1armKiwbQNmB3YJP3q4

Solution 1: through a text editor exploiting more

bandit25@bandit:~$ ls -al
total 40
drwxr-xr-x  2 root     root     4096 Jul 17 15:57 .
drwxr-xr-x 70 root     root     4096 Jul 17 15:58 ..
-rw-r-----  1 bandit25 bandit25   33 Jul 17 15:57 .bandit24.password
-r--------  1 bandit25 bandit25 1679 Jul 17 15:57 bandit26.sshkey
-rw-r-----  1 bandit25 bandit25  151 Jul 17 15:57 .banner
-rw-r--r--  1 root     root      220 Mar 31 08:41 .bash_logout
-rw-r--r--  1 root     root     3771 Mar 31 08:41 .bashrc
-rw-r-----  1 bandit25 bandit25   66 Jul 17 15:57 .flag
-rw-r-----  1 bandit25 bandit25    4 Jul 17 15:57 .pin
-rw-r--r--  1 root     root      807 Mar 31 08:41 .profile

andit25@bandit:~$ cat /etc/passwd | grep "bandit26"
bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext
bandit25@bandit:~$ cat /usr/bin/showtext
#!/bin/sh

export TERM=linux

exec more ~/text.txt
exit 0

bandit25@bandit:~$ ssh -i bandit26.sshkey [bandit26@bandit.labs.overthewire.org](mailto:bandit26@bandit.labs.overthewire.org) -p 2220

using editor

v

:e /etc/bandit_pass/bandit26

s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ

Solution 2: start a shell with bash interpreter

again enter text editor using v

:set shell=/bin/bash  (enter)

:shell (enter) (starts a shell)

bandit26@bandit:~$ cat /etc/bandit_pass/bandit26
s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ