# Bandit Level 11 → Level 12

## Level Goal

The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

## Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

## Helpful Reading Material

- [Rot13 on Wikipedia](https://en.wikipedia.org/wiki/Rot13)

### Solution:

From the previous level, we have the password:

**Password:** dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr

To SSH into the server, use the following command:

**Command:**

ssh [bandit11@bandit.labs.overthewire.org](mailto:bandit1@bandit.labs.overthewire.org) -p 2220

enter the password: dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr

bandit11@bandit:~$ ls
data.txt
bandit11@bandit:~$ cat data.txt | tr '[a-zA-Z]' '[n-za-mN-ZA-M]'
The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4

The `tr` command is used for translating or deleting characters. In the context of ROT13 decryption, it is used to map each letter of the alphabet to another letter that is 13 positions away from it. The syntax `'[a-zA-Z]' '[n-za-mN-ZA-M]'` specifies two sets of characters:

- The first set `'[a-zA-Z]'` includes all lowercase and uppercase letters from `a` to `z` and `A` to `Z`.
- The second set `'[n-za-mN-ZA-M]'` specifies the target characters for the translation.