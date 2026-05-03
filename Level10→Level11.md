# Bandit Level 10 → Level 11

## Goal
The password is stored in `data.txt` as base64-encoded data.

## Solution
1. Connected to the server using SSH: 
```
ssh -p 2220 bandit10@bandit.labs.overthewire.org
```
2. Listed files in the directory:
```
ls
```
3. Found a file named `data.txt`
4. Decoded the base64-encoded data from `data.txt`:
```
base64 -d data.txt
```

## Result
The password was found in `data.txt` after decoding the base64-encoded data.

## Learning
- I learned how base64 encoding works and how to encode and decode data using the `base64` command.
- Basic syntax:
  - `base64 [file]` → encodes a file
  - `base64 -d [file]` → decodes base64-encoded data  
