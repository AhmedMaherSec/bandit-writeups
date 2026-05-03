# Bandit Level 12 → Level 13

## Goal
The password is in `data.txt`, which is a hexdump of a repeatedly compressed file. Work in a temporary directory to extract it.

## Solution
1. Connected to the server using SSH: 
```
ssh -p 2220 bandit12@bandit.labs.overthewire.org
```
2. Listed files in the directory:
```
ls
```
3. Found a file named `data.txt`
4. Created a temporary working directory using `mktemp -d`, which returned `/tmp/tmp.xNyGxAjpWv` as the working path.
5. I copied `data.txt` to the temporary directory.
```
cp data.txt /tmp/tmp.xNyGxAjpWv
```
6. Navigated to the temporary directory to continue the work there.
```
cd /tmp/tmp.xNyGxAjpWv
```
7. Reversed the hexdump format of `data.txt` into a readable ASCII file using :
```
xxd -r data.txt > original
```
8. Iteratively inspected file types using `file` and extracted multiple compression layers by applying the appropriate method at each step.
```
file original
```
9. Renamed files when necessary to match the correct format before extraction, based on the identified file type at each step.
```
mv original original.gz
```
```
mv original original.bz2
```

10. Progressively decompressed the file using multiple tools based on its type.
```
gunzip original.gz
```
```
bunzip2 original.bz2
```
```
tar -xvf original.tar
```

## Result
The password was found after repeatedly identifying file types and extracting multiple compressed layers until reaching the final readable file.
## Learning
- I learned how to create a temporary working directory using `mktemp` and perform operations safely inside it.
- Basic syntax:
  - `mktemp ` → temporary file
  - `mktemp -d` → temporary directory

- I learned how to handle hexdump files and convert them back to their original binary format using `xxd`.
- Basic syntax:
  - `xxd file` → create hexdump
  - `xxd -r file` → reverse hexdump to original data
 
- I learned about different compression formats such as `gzip` and `bzip2`, and how to extract them using `gunzip` and `bunzip2`.
- I learned the difference between compression (reducing size) and archiving (combining files).
- I learned how to use `tar` for archiving and extraction:
  - `tar -cvf` → create archive
  - `tar -xvf` → extract archive
