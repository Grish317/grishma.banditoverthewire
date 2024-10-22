# Bandit Level 28 → Level 29

## Level Goal

There is a git repository at `ssh://bandit28-git@localhost/home/bandit28-git/repo` via the port `2220`. The password for the user `bandit28-git` is the same as for the user `bandit28`.

Clone the repository and find the password for the next level.

## Commands you may need to solve this level

git

bandit28@bandit:~$ mkdir /tmp/kamisama28
bandit28@bandit:~$ cd /tmp/kamisama28
bandit28@bandit:/tmp/kamisama27$ git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
Cloning into 'repo'...

bandit28-git@localhost's password: Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN

bandit28@bandit:/tmp/kamisama28$ ls -al
total 56
drwxrwxr-x    3 bandit28 bandit28  4096 Jul 18 17:08 .
drwxrwx-wt 1175 root     root     45056 Jul 18 17:09 ..
drwxrwxr-x    3 bandit28 bandit28  4096 Jul 18 17:09 repo
bandit28@bandit:/tmp/kamisama28$ cd repo
bandit28@bandit:/tmp/kamisama28/repo$ ls -al
total 16
drwxrwxr-x 3 bandit28 bandit28 4096 Jul 18 17:09 .
drwxrwxr-x 3 bandit28 bandit28 4096 Jul 18 17:08 ..
drwxrwxr-x 8 bandit28 bandit28 4096 Jul 18 17:09 .git
-rw-rw-r-- 1 bandit28 bandit28  111 Jul 18 17:09 [README.md](http://readme.md/)
bandit28@bandit:/tmp/kamisama28/repo$ cat [README.md](http://readme.md/)

# Bandit Notes

Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx

bandit28@bandit:/tmp/kamisama28/repo/.git$ git log
commit 8cbd1e08d1879415541ba19ddee3579e80e3f61a (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla [morla@overthewire.org](mailto:morla@overthewire.org)
Date:   Wed Jul 17 15:57:30 2024 +0000

```
fix info leak

```

commit 73f5d0435070c8922da12177dc93f40b2285e22a
Author: Morla Porla [morla@overthewire.org](mailto:morla@overthewire.org)
Date:   Wed Jul 17 15:57:30 2024 +0000

```
add missing data

```

commit 5f7265568c7b503b276ec20f677b68c92b43b712
Author: Ben Dover [noone@overthewire.org](mailto:noone@overthewire.org)
Date:   Wed Jul 17 15:57:30 2024 +0000

```
initial commit of README.md

```

bandit28@bandit:/tmp/kamisama28/repo/.git$ git checkout 5f7265568c7b503b276ec20f677b68c92b43b712
fatal: this operation must be run in a work tree
bandit28@bandit:/tmp/kamisama28/repo/.git$ git show 5f7265568c7b503b276ec20f677b68c92b43b712
commit 5f7265568c7b503b276ec20f677b68c92b43b712
Author: Ben Dover [noone@overthewire.org](mailto:noone@overthewire.org)
Date:   Wed Jul 17 15:57:30 2024 +0000

```
initial commit of README.md

```

diff --git a/README.md b/README.md
new file mode 100644
index 0000000..7ba2d2f
--- /dev/null
+++ b/README.md
@@ -0,0 +1,8 @@
+# Bandit Notes
+Some notes for level29 of bandit.
+
+## credentials
+
+- username: bandit29
+- password: <TBD>

bandit28@bandit:/tmp/kamisama28/repo/.git$ git show 8cbd1e08d1879415541ba19ddee3579e80e3f61a
commit 8cbd1e08d1879415541ba19ddee3579e80e3f61a (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla [morla@overthewire.org](mailto:morla@overthewire.org)
Date:   Wed Jul 17 15:57:30 2024 +0000

```
fix info leak

```

diff --git a/README.md b/README.md
index d4e3b74..5c6457b 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for level29 of bandit.

## credentials

- username: bandit29
-- password: 4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7
+- password: xxxxxxxxxx