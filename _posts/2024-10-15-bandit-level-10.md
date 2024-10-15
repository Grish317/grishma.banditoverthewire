# Bandit Level 9 → Level 10

## Level Goal

The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

## Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

### Solution:

From the previous level, we have the password:

**Password:** 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

To SSH into the server, use the following command:

**Command:**

ssh [bandit9@bandit.labs.overthewire.org](mailto:bandit1@bandit.labs.overthewire.org) -p 2220

enter the password: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ strings data.txt | grep "="
,=W$j
*N========== the
wP=LWv
|Co=}
QY=n
========== password
i="\
========== is
=n\9p
=q|(
Io=/[.
w========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
+)=dY
bandit9@bandit:~$