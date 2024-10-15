# Bandit Level 8 → Level 9

## Level Goal

The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once

## Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

## Helpful Reading Material

- [Piping and Redirection](https://ryanstutorials.net/linuxtutorial/piping.php)

### Solution:

From the previous level, we have the password:

**Password:** dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

To SSH into the server, use the following command:

**Command:**

ssh [bandit8@bandit.labs.overthewire.org](mailto:bandit1@bandit.labs.overthewire.org) -p 2220

enter the password: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ cat data.txt | sort | uniq -c | grep '1 '
1 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
bandit8@bandit:~$

### Command Explanation:

- **`cat data.txt`**: Reads the contents of `data.txt`.
- **`| sort`**: Sorts the lines alphabetically.
- **`| uniq -c`**: Counts the occurrences of each unique line.
- **`| grep '1 '`**: Filters and displays only those lines that appear exactly once (`uniq -c` prefixes lines with the count, so lines with "1 " indicate they appeared exactly once).