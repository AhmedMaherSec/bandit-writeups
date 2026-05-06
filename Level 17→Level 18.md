# Bandit Level 17 → Level 18

## Goal
The Password is found by identifying the line that differs between `passwords.old` and `passwords.new`.

## Solution

1. Connected to the server using SSH (using a private SSH key) : 
```
ssh -i sshkey2.private -p 2220 bandit17@bandit.labs.overthewire.org
```
2. Used the `diff` command to compare both files and find the changed line:
```
diff passwords.new passwords.old
```

## Result
The password for the next level was identified by comparing the two files.

## Learning
- I learned that `diff` helps compare files line by line to find what has changed between them.
- Basic syntax:
  - `diff file1 file2`
