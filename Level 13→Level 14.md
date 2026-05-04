# Bandit Level 13 → Level 14
## Goal
Log in as `bandit14` using the given SSH key and retrieve the password from `/etc/bandit_pass/bandit14`.

## Solution
1. Connected to the server using SSH: 
```
ssh -p 2220 bandit13@bandit.labs.overthewire.org
```
2. Listed files in the directory:
```
ls
```
3. Found a file named `sshkey.private`
4. After exiting the SSH session, I downloaded the private key file `sshkey.private` to my local machine .
```
scp -P 2220 bandit13@bandit.labs.overthewire.org:/home/bandit13/sshkey.private .
```
5. Logged in to `bandit14` using the private SSH key.
```
ssh -i sshkey.private -p 2220 bandit14@bandit.labs.overthewire.org
```
6. Accessed the password file and read its contents to obtain the password for the current level.
```
cat /etc/bandit_pass/bandit14
```


## Result
I authenticated to `bandit14` using a private SSH key instead of a password, then successfully retrieved the password for the current level.

## Learning
- I learned that SSH key authentication is a secure alternative to password-based login.
- I learned that the `-i` option in `ssh` allows specifying a private key file for authentication.
- I learned that `scp` is used to transfer files securely between a local machine and a remote server.
- Basic syntax:
  - Upload: `scp file user@host:/path`
  - Download: `scp user@host:/path .`
