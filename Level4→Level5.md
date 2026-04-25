# Bandit Level 4 → Level 5

## Goal
Find the password in the only human-readable file in the `inhere` directory.

## Solution
1. Connected to the server using SSH: 
```
ssh -p 2220 bandit4@bandit.labs.overthewire.org
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
5. Listed files in the `inhere`:
```
ls 
```
6. Found multiple files in the directory.

7. Used the following command to determine the type of each file:
```
file ./*
```
8. Found a file named `-file07` that is identified as ASCII text (human-readable).   
Output:
````
./-file07: ASCII text
```
10. Read the file:
```
cat ./"-file07"
```
## Result
The password for the next level was found in the file `-file07`.

## Learning
- I learned that the `file` command is used to determine the type of a file.
- Basic syntax: `file [filename]`
- It can also be used with multiple files: `file ./*`
