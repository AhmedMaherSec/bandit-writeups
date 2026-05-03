# Bandit Level 11 → Level 12

## Goal
The password is in `data.txt`, where letters are rotated by 13 positions (ROT13).

## Solution
1. Connected to the server using SSH: 
```
ssh -p 2220 bandit11@bandit.labs.overthewire.org
```
2. Listed files in the directory:
```
ls
```
3. Found a file named `data.txt`
4. Decoded the ROT13 encoding in `data.txt`:
```
tr [a-mA-Mn-zN-Z] [n-zN-Za-mA-M] < data.txt
```

## Result
The password was found after decoding the ROT13-encoded data in `data.txt`.

## Learning
- I learned that the `tr` command is used to translate characters from one set to another.
- Basic syntax:
  - `tr [SET1] [SET2]`
- I learned that `tr` does not accept files directly, so input redirection `<` is used instead.
  - `tr [SET1] [SET2] < file` 
