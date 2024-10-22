# Bandit Level 30 → Level 31

## Level Goal

There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo` via the port `2220`. The password for the user `bandit30-git` is the same as for the user `bandit30`.

Clone the repository and find the password for the next level.

## Commands you may need to solve this level

git

### Solution:

From the previous level, we have the password for bandit30:

**Password:** qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL

bandit30@bandit:~$ mkdir /tmp/kamisama30
bandit30@bandit:~$ cd /tmp/kamisama30
bandit30@bandit:/tmp/kamisama30$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
Cloning into 'repo'...
bandit30-git@localhost's password:qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), done.
bandit30@bandit:/tmp/kamisama30$ ls -al
total 60
drwxrwxr-x    3 bandit30 bandit30  4096 Jul 18 17:52 .
drwxrwx-wt 1208 root     root     49152 Jul 18 17:52 ..
drwxrwxr-x    3 bandit30 bandit30  4096 Jul 18 17:52 repo
bandit30@bandit:/tmp/kamisama30$ cd repo
bandit30@bandit:/tmp/kamisama30/repo$ ls -al
total 16
drwxrwxr-x 3 bandit30 bandit30 4096 Jul 18 17:52 .
drwxrwxr-x 3 bandit30 bandit30 4096 Jul 18 17:52 ..
drwxrwxr-x 8 bandit30 bandit30 4096 Jul 18 17:52 .git
-rw-rw-r-- 1 bandit30 bandit30   30 Jul 18 17:52 [README.md](http://readme.md/)
bandit30@bandit:/tmp/kamisama30/repo$ cat [README.md](http://readme.md/)
just an epmty file... muahaha

bandit30@bandit:/tmp/kamisama30/repo$ cd .git

bandit30@bandit:/tmp/kamisama30/repo/.git$ ls -al
total 52
drwxrwxr-x 8 bandit30 bandit30 4096 Jul 18 17:52 .
drwxrwxr-x 3 bandit30 bandit30 4096 Jul 18 17:52 ..
drwxrwxr-x 2 bandit30 bandit30 4096 Jul 18 17:52 branches
-rw-rw-r-- 1 bandit30 bandit30  281 Jul 18 17:52 config
-rw-rw-r-- 1 bandit30 bandit30   73 Jul 18 17:52 description
-rw-rw-r-- 1 bandit30 bandit30   23 Jul 18 17:52 HEAD
drwxrwxr-x 2 bandit30 bandit30 4096 Jul 18 17:52 hooks
-rw-rw-r-- 1 bandit30 bandit30  137 Jul 18 17:52 index
drwxrwxr-x 2 bandit30 bandit30 4096 Jul 18 17:52 info
drwxrwxr-x 3 bandit30 bandit30 4096 Jul 18 17:52 logs
drwxrwxr-x 4 bandit30 bandit30 4096 Jul 18 17:52 objects
-rw-rw-r-- 1 bandit30 bandit30  172 Jul 18 17:52 packed-refs
drwxrwxr-x 5 bandit30 bandit30 4096 Jul 18 17:52 refs

bandit30@bandit:/tmp/kamisama30/repo/.git$ cat packed-refs

pack-refs with: peeled fully-peeled sorted

60410f42e05023128098dc1f6991c75e6ae02e47 refs/remotes/origin/master
84368f3a7ee06ac993ed579e34b8bd144afad351 refs/tags/secret

bandit30@bandit:/tmp/kamisama30/repo/.git$ git show 84368f3a7ee06ac993ed579e34b8bd144afad351
fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy