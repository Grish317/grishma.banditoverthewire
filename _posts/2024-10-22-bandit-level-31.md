# Bandit Level 31 → Level 32

## Level Goal

There is a git repository at `ssh://bandit31-git@localhost/home/bandit31-git/repo` via the port `2220`. The password for the user `bandit31-git` is the same as for the user `bandit31`.

Clone the repository and find the password for the next level.

## Commands you may need to solve this level

git

### Solution:

From the previous level, we have the password for bandit30:

**Password:** fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy

bandit31@bandit:~$ mkdir /tmp/kamisama31
bandit31@bandit:~$ cd /tmp/kamisama31
bandit31@bandit:/tmp/kamisama31$ git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
Cloning into 'repo'...
bandit31-git@localhost's password: fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), done.

bandit30@bandit:/tmp/kamisama31$ cd repo

bandit31@bandit:/tmp/kamisama31/repo$ ls -al
total 20
drwxrwxr-x 3 bandit31 bandit31 4096 Jul 18 17:58 .
drwxrwxr-x 3 bandit31 bandit31 4096 Jul 18 17:58 ..
drwxrwxr-x 8 bandit31 bandit31 4096 Jul 18 18:01 .git
-rw-rw-r-- 1 bandit31 bandit31    6 Jul 18 17:58 .gitignore
-rw-rw-r-- 1 bandit31 bandit31  147 Jul 18 17:58 [README.md](http://readme.md/)

bandit31@bandit:/tmp/kamisama31/repo$ cat [README.md](http://readme.md/)
This time your task is to push a file to the remote repository.

Details:
File name: key.txt
Content: 'May I come in?'
Branch: master

bandit31@bandit:/tmp/kamisama31/repo$ echo "May I come in?" > key.txt

bandit31@bandit:/tmp/kamisama31/repo$ cat .gitignore
*.txt

bandit31@bandit:/tmp/kamisama31/repo$ git add -f key.txt
bandit31@bandit:/tmp/kamisama31/repo$ git commit -m "Added key.txt"
[master 4f92449] Added key.txt
1 file changed, 1 insertion(+)
create mode 100644 key.txt

bandit31@bandit:/tmp/kamisama31/repo$ git push origin master

remote: Well done! Here is the password for the next level:
remote: 3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K