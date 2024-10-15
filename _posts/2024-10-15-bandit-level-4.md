# Bandit Level 3 → Level 4

## Level Goal

The password for the next level is stored in a hidden file in the **inhere** directory.

## Commands you may need to solve this level

[ls](https://man7.org/linux/man-pages/man1/ls.1.html) , [cd](https://man7.org/linux/man-pages/man1/cd.1p.html) , [cat](https://man7.org/linux/man-pages/man1/cat.1.html) , [file](https://man7.org/linux/man-pages/man1/file.1.html) , [du](https://man7.org/linux/man-pages/man1/du.1.html) , [find](https://man7.org/linux/man-pages/man1/find.1.html)

### Solution:

From the previous level, we have the password:

**Password:** MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

To SSH into the server, use the following command:

**Command:**

ssh [bandit3@bandit.labs.overthewire.org](mailto:bandit1@bandit.labs.overthewire.org) -p 2220

enter the password: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

### Step 1: List Files in the Current Directory

```
bandit3@bandit:~$ ls
inhere
```

### Step 2: Change to the `inhere` Directory

```
bandit3@bandit:~$ cd inhere
```

### Step 3: List All Files, Including Hidden Ones

The `ls -a` command lists all files and directories in the current directory, including hidden ones. 

```
bandit3@bandit:~/inhere$ ls -a
.  ..  ...Hiding-From-You
```

### Step 4: View the Contents of the Hidden File

```
bandit3@bandit:~/inhere$ cat ...Hiding-From-You
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```