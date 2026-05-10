# Bandit Level 19 → Level 20

## Goal
The password can be retrieved from `/etc/bandit_pass` using the setuid binary in the home directory.

## Solution

1. Connected to the server using SSH: 
```
ssh -p 2220 bandit19@bandit.labs.overthewire.org
```
2. Listed the files in the home directory and identified a setuid binary named `bandit20-do`.
```
ls -lh
```
3. Executed the binary without arguments to understand how it should be used:
```
./bandit20-do
```
4. The output explained that the binary can run commands as its owner when a command is provided as an argument :
```
Run a command as another user.
Example: ./bandit20-do whoami
```
5. Used the setuid binary to execute the `cat` command on the password file with elevated privileges:
```
./bandit20-do cat /etc/bandit_pass/bandit20
```

## Result
The password for the next level was obtained after using the setuid executable.

## Learning
- I learned that the `setuid` special permission allows an executable to run with the file owner's privileges instead of the current user's privileges.
