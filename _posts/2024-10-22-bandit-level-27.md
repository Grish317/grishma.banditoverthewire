# Bandit Level 27 → Level 28

## Level Goal

There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo` via the port `2220`. The password for the user `bandit27-git` is the same as for the user `bandit27`.

Clone the repository and find the password for the next level.

## Commands you may need to solve this level

git

Solution:

bandit27@bandit:~$ mkdir /tmp/kamisama27
bandit27@bandit:~$ cd /tmp/kamisama27
bandit27@bandit:/tmp/kamisama27$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
Cloning into 'repo'...

bandit27-git@localhost's password:
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
Receiving objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
bandit27@bandit:/tmp/kamisama27$ ls -al
total 56
drwxrwxr-x    3 bandit27 bandit27  4096 Jul 18 17:04 .
drwxrwx-wt 1174 root     root     45056 Jul 18 17:05 ..
drwxrwxr-x    3 bandit27 bandit27  4096 Jul 18 17:04 repo
bandit27@bandit:/tmp/kamisama27$ cd repo
bandit27@bandit:/tmp/kamisama27/repo$ ls
README
bandit27@bandit:/tmp/kamisama27/repo$ cat README
The password to the next level is: Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN

Then login as bandit 28

┌─[grishma@parrot]─[~]
└──╼ $ssh [bandit28@bandit.labs.overthewire.org](mailto:bandit28@bandit.labs.overthewire.org) -p 2220

pass: Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN