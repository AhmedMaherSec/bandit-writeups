# Bandit Level 7 → Level 8

## Goal
Find the password stored in the file `data.txt` next to the word `millionth`.

## Solution
1. Connected to the server using SSH: 
```
ssh -p 2220 bandit7@bandit.labs.overthewire.org
```
2. Listed files in the directory:
```
ls
```
3. Found a file named `data.txt`
4. Searched the file `data.txt` for the word `millionth`:
```
grep "millionth" data.txt
```

## Result
The password for the next level was found in the file `data.txt` next to the word `millionth`.

## Learning
- I learned that the `grep` command is used to search for a specific pattern inside a file.
- Basic syntax: `grep [options] [pattern] [file]`
