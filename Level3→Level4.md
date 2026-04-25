# Bandit Level 3 → Level 4

## Goal
Find the password in a hidden file in the `inhere` directory.

## Solution
1. Connected to the server using SSH: 
```
ssh -p 2220 bandit3@bandit.labs.overthewire.org
```
2. Listed files in the directory:
```
ls
```
3. Found a directory named `inhere` 
4. Changed directory to `inhere` :
```
cd inhere
```
5. Listed files in the `inhere` including hidden files:
```
ls -a 
```
6. Found a file named `...Hiding-From-You` 
7. Read the file:
```
cat ./"...Hiding-From-You"
```
## Result
The password for the next level was found in the file `...Hiding-From-You`.

## Learning
- I learned that the `-a` option with `ls` shows all files, including hidden ones.
