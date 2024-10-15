# Bandit Level 12 → Level 13

## Level Goal

The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)

## Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd, mkdir, cp, mv, file

## Helpful Reading Material

- [Hex dump on Wikipedia](https://en.wikipedia.org/wiki/Hex_dump)

### Solution:

From the previous level, we have the password:

**Password:** 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4

To SSH into the server, use the following command:

**Command:**

ssh [bandit12@bandit.labs.overthewire.org](mailto:bandit1@bandit.labs.overthewire.org) -p 2220

enter the password: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4

bandit12@bandit:~$ ls
data.txt
bandit12@bandit:~$ file data.txt
data.txt: ASCII text
bandit12@bandit:~$ mkdir /tmp/decompress
bandit12@bandit:~$ cd /tmp/decompress
bandit12@bandit:/tmp/decompress$ xxd -r data.txt data
xxd: data.txt: No such file or directory
bandit12@bandit:/tmp/decompress$ xxd -r ~/data.txt data
bandit12@bandit:/tmp/decompress$ ls
data
bandit12@bandit:/tmp/decompress$ file data
data: gzip compressed data, was "data2.bin", last modified: Sun Jun 16 02:47:25 2024, max compression, from Unix, original size modulo 2^32 578
bandit12@bandit:/tmp/decompress$ mv data data.gz
bandit12@bandit:/tmp/decompress$ gunzip data.gz
bandit12@bandit:/tmp/decompress$ ls
data
bandit12@bandit:/tmp/decompress$ file data
data: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/decompress$ mv data data.bz2
bandit12@bandit:/tmp/decompress$ bunzip2 data.bz2
bandit12@bandit:/tmp/decompress$ ls
data
bandit12@bandit:/tmp/decompress$ file data
data: gzip compressed data, was "data4.bin", last modified: Sun Jun 16 02:47:25 2024, max compression, from Unix, original size modulo 2^32 20480
bandit12@bandit:/tmp/decompress$ mv data data.gz
bandit12@bandit:/tmp/decompress$ gunzip data.gz
bandit12@bandit:/tmp/decompress$ ls
data
bandit12@bandit:/tmp/decompress$ file data
data: POSIX tar archive (GNU)
bandit12@bandit:/tmp/decompress$ mv data data.tar
bandit12@bandit:/tmp/decompress$ tar -xf data.tar
bandit12@bandit:/tmp/decompress$ ls
data5.bin  data.tar
bandit12@bandit:/tmp/decompress$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/decompress$ mv data5.bin data5.tar
bandit12@bandit:/tmp/decompress$ tar -xf data5.tar
bandit12@bandit:/tmp/decompress$ ls
data5.tar  data6.bin  data.tar
bandit12@bandit:/tmp/decompress$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/decompress$ mv data6.bin data6.bz2
bandit12@bandit:/tmp/decompress$ bunzip2 data6.bz2
bandit12@bandit:/tmp/decompress$ ls
data5.tar  data6  data.tar
bandit12@bandit:/tmp/decompress$ file data6
data6: POSIX tar archive (GNU)
bandit12@bandit:/tmp/decompress$ mv data6 data6.tar
bandit12@bandit:/tmp/decompress$ tar -xf data6.tar
bandit12@bandit:/tmp/decompress$ ls
data5.tar  data6.tar  data8.bin  data.tar
bandit12@bandit:/tmp/decompress$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Sun Jun 16 02:47:25 2024, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/decompress$ mv data8.bin data8.gz
bandit12@bandit:/tmp/decompress$ gunzip data8.gz
bandit12@bandit:/tmp/decompress$ ls
data5.tar  data6.tar  data8  data.tar
bandit12@bandit:/tmp/decompress$ file data8
data8: ASCII text
bandit12@bandit:/tmp/decompress$ cat data8
The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn