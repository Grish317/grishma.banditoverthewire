# Bandit Level 29 → Level 30

## Level Goal

There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo` via the port `2220`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.

## Commands you may need to solve this level

git

### Solution:

From the previous level, we have the password for bandit29:

**Password:** 4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7

bandit29@bandit:~$ mkdir /tmp/kamisama29
bandit29@bandit:~$ cd /tmp/kamisama29
bandit29@bandit:/tmp/kamisama29$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
Cloning into 'repo'...

bandit29-git@localhost's password: 4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7
remote: Enumerating objects: 16, done.
remote: Counting objects: 100% (16/16), done.
remote: Compressing objects: 100% (11/11), done.
remote: Total 16 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (16/16), done.
Resolving deltas: 100% (2/2), done.
bandit29@bandit:/tmp/kamisama29$ ls -al
total 60
drwxrwxr-x    3 bandit29 bandit29  4096 Jul 18 17:46 .
drwxrwx-wt 1201 root     root     49152 Jul 18 17:46 ..
drwxrwxr-x    3 bandit29 bandit29  4096 Jul 18 17:46 repo
bandit29@bandit:/tmp/kamisama29$ cd repo
bandit29@bandit:/tmp/kamisama29/repo$ ls -al
total 16
drwxrwxr-x 3 bandit29 bandit29 4096 Jul 18 17:46 .
drwxrwxr-x 3 bandit29 bandit29 4096 Jul 18 17:46 ..
drwxrwxr-x 8 bandit29 bandit29 4096 Jul 18 17:46 .git
-rw-rw-r-- 1 bandit29 bandit29  131 Jul 18 17:46 [README.md](http://readme.md/)
bandit29@bandit:/tmp/kamisama29/repo$ cat [README.md](http://readme.md/)

# Bandit Notes

Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>

bandit29@bandit:/tmp/kamisama29/repo/.git$ git branch -a

- master
remotes/origin/HEAD -> origin/master
remotes/origin/dev
remotes/origin/master
remotes/origin/sploits-dev
bandit29@bandit:/tmp/kamisama29/repo/.git$ cd ..
bandit29@bandit:/tmp/kamisama29/repo$ git checkout dev
branch 'dev' set up to track 'origin/dev'.
Switched to a new branch 'dev'
bandit29@bandit:/tmp/kamisama29/repo$ ls -al
total 20
drwxrwxr-x 4 bandit29 bandit29 4096 Jul 18 17:49 .
drwxrwxr-x 3 bandit29 bandit29 4096 Jul 18 17:46 ..
drwxrwxr-x 2 bandit29 bandit29 4096 Jul 18 17:49 code
drwxrwxr-x 8 bandit29 bandit29 4096 Jul 18 17:49 .git
-rw-rw-r-- 1 bandit29 bandit29 134 Jul 18 17:49 [README.md](http://readme.md/)
bandit29@bandit:/tmp/kamisama29/repo$ cat [README.md](http://readme.md/)

# Bandit Notes

Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL