# Bandit Level 13 → Level 14

## Level Goal

The password for the next level is stored in **/etc/bandit_pass/bandit14 and can only be read by user bandit14**. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. **Note:** **localhost** is a hostname that refers to the machine you are working on

## Commands you may need to solve this level

ssh, telnet, nc, openssl, s_client, nmap

## Helpful Reading Material

- [SSH/OpenSSH/Keys](https://help.ubuntu.com/community/SSH/OpenSSH/Keys)

### Solution:

From the previous level, we have the password:

**Password:** FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

To SSH into the server, use the following command:

**Command:**

ssh [bandit13@bandit.labs.overthewire.org](mailto:bandit1@bandit.labs.overthewire.org) -p 2220

enter the password: FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

bandit13@bandit:~$ ls -a
.  ..  .bash_logout  .bashrc  .profile  sshkey.private
bandit13@bandit:~$ exit
logout
Connection to [bandit.labs.overthewire.org](http://bandit.labs.overthewire.org/) closed.

┌─[✗]─[grishma@parrot]─[~]
└──╼ $scp -P 2220 [bandit13@bandit.labs.overthewire.org](mailto:bandit13@bandit.labs.overthewire.org):~/sshkey.private .

Here:

- The `scp` command is used here to copy the file `sshkey.private` from the remote server (`bandit.labs.overthewire.org`) to the current directory (`.`) on your local machine.
- `P 2220` specifies that the SSH connection should use port `2220` instead of the default SSH port (`22`).
- `~/sshkey.private` is the path to the file `sshkey.private` in the home directory (`~`) of the user `bandit13` on the remote server.
- `.` indicates the current directory on your local machine where you want to place the copied file.

Now we have copied the file. Then,

┌─[grishma@parrot]─[~]
└──╼ $chmod 400 sshkey.private

`chmod 400 sshkey.private` is used to set the file permissions of `sshkey.private` to read-only for the owner (`bandit14`)

┌─[grishma@parrot]─[~]
└──╼ $ssh -i sshkey.private [bandit14@bandit.labs.overthewire.org](mailto:bandit14@bandit.labs.overthewire.org) -p 2220

Here, the `-i` option specifies the path to the private key file (`sshkey.private`). This private key file is used for authentication instead of a password.

Hence we get connected to bandit4 without password.

As per the description, we can get the password for bandit14 in **/etc/bandit_pass/bandit14.**

So,

bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS