# Bandit Level 10 → Level 11

## Level Goal

The password for the next level is stored in the file **data.txt**, which contains base64 encoded data

## Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

## Helpful Reading Material

- [Base64 on Wikipedia](https://en.wikipedia.org/wiki/Base64)

### Solution:

From the previous level, we have the password:

**Password:** FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

To SSH into the server, use the following command:

**Command:**

ssh [bandit10@bandit.labs.overthewire.org](mailto:bandit1@bandit.labs.overthewire.org) -p 2220

enter the password: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ cat data.txt | base64 -d
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
bandit10@bandit:~$

Here, **`| base64 -d`**: Decodes the Base64-encoded data that is piped into it from `cat data.txt`.