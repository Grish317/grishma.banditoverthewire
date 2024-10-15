# Bandit Level 7 → Level 8

## Level Goal

The password for the next level is stored in the file **data.txt** next to the word **millionth**

## Commands you may need to solve this level

[man](https://man7.org/linux/man-pages/man1/man.1.html), grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

### Solution:

From the previous level, we have the password:

**Password:** morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

To SSH into the server, use the following command:

**Command:**

ssh [bandit7@bandit.labs.overthewire.org](mailto:bandit1@bandit.labs.overthewire.org) -p 2220

enter the password: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

bandit7@bandit:~$ ls
data.txt

bandit7@bandit:~$ grep "millionth" data.txt
millionth	dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc