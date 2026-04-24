# Bandit Level 2 → Level 3

## Goal
Find the password in a file in the home directory called `--spaces in this filename--`

## Solution
1. Connected to the server using SSH: 
```
ssh -p 2220 bandit2@bandit.labs.overthewire.org
```
2. Verified my current directory:
```
pwd
```
3. Listed files in the directory:
```
ls
```
4. Found a file named `--spaces in this filename--` in the directory

5. Read the file:
```
cat -- "--spaces in this filename--"
```
## Result
The password for the next level was found in the file `--spaces in this filename--`.

## Learning
- I learned that `pwd` shows my current working directory.
- I learned that `--` is used to stop option parsing, allowing me to safely work with files that start with special characters.
- I learned that quotes `" "` keep the text inside as one argument and prevent shell interpretation.

### Alternative methods
- To handle file names with spaces or special characters, I can use:
```cat ./"--spaces in this filename--"```
- or
```cat -- "--spaces in this filename--"```
