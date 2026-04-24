# Bandit Level 0

## Goal
Connect to the server and find the password for the next level.

## Solution
1. Connected to the server using SSH: 
```
ssh -p 2220 bandit0@bandit.labs.overthewire.org
```
2. Listed files in the directory:
```
ls
```
3. Found a file named `readme` in the directory

4. Read the file:
```
cat readme
```
## Result
The password for the next level was found in the file `readme`.

## Learning
- `ssh` is used to connect to a remote server
- Default SSH port is `22`
- Basic SSH syntax:
```
ssh -p [port] [user]@[hostname or ip address]
```
- `ls` lists files and directories
- `cat` is used to read file content
