# Bandit Level 26 → Level 27

## Level Goal

Good job getting a shell! Now hurry and grab the password for bandit27!

## Commands you may need to solve this level

ls

### Solution:

From the previous level, we have the password:

**Password:** s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ

To SSH into the server, use the following command:

**Command:**

ssh [bandit26@bandit.labs.overthewire.org](mailto:bandit1@bandit.labs.overthewire.org) -p 2220

enter the password: s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ

Run the shell in the same way as bandit 25 to 26 Solution 2

Then:

bandit26@bandit:~$ ls -al
total 44
drwxr-xr-x  3 root     root      4096 Jul 17 15:57 .
drwxr-xr-x 70 root     root      4096 Jul 17 15:58 ..
-rwsr-x---  1 bandit27 bandit26 14880 Jul 17 15:57 bandit27-do
-rw-r--r--  1 root     root       220 Mar 31 08:41 .bash_logout
-rw-r--r--  1 root     root      3771 Mar 31 08:41 .bashrc
-rw-r--r--  1 root     root       807 Mar 31 08:41 .profile
drwxr-xr-x  2 root     root      4096 Jul 17 15:57 .ssh
-rw-r-----  1 bandit26 bandit26   258 Jul 17 15:57 text.txt
bandit26@bandit:~$ ./bandit27-do
Run a command as another user.
Example: ./bandit27-do id
bandit26@bandit:~$ ./bandit27-do id
uid=11026(bandit26) gid=11026(bandit26) euid=11027(bandit27) groups=11026(bandit26)
bandit26@bandit:~$ ./bandit27-do cat /etc/bandit_pass/bandit27
upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB