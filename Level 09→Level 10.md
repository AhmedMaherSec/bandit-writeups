# Bandit Level 9 → Level 10

## Goal
The password is in `data.txt` within readable strings preceded by `=` characters.

## Solution
1. Connected to the server using SSH: 
```
ssh -p 2220 bandit9@bandit.labs.overthewire.org
```
2. Listed files in the directory:
```
ls
```
3. Found a file named `data.txt`
4. Extracted human-readable strings from `data.txt` :
```
strings data.txt | grep -E "=+"
```

## Result
The password was found after extracting readable data from a large non-readable file.

## Learning
- I learned that the `strings` command is used to extract human-readable text from binary files.
  - `strings [options] file`
- I learned that `grep -E` is used to search for patterns using Extended Regular Expressions (ERE).
  - `grep -E [regex] [file]` 
