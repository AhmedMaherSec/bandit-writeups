# Bandit Level 1 → Level 2

## Goal
Find the password in a file in the home directory and use it to log in to the next level via SSH.

## Solution
1. Connected to the server using SSH: 
```
ssh -p 2220 bandit1@bandit.labs.overthewire.org
```
2. I ensured I am in the home directory :
```
cd ~
```
3. Listed files in the directory:
```
ls
```
4. Found a file named `-` in the directory

5. Read the file:
```
cat ./-
```
## Result
The password for the next level was found in the file `-`.

## Learning
- I learned how to read files with special names like `-`
- Instead of using `cat -` , I use:
```
cat ./-
```
- This avoids `-` being interpreted as a command option.
