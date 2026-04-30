# Bandit Level 5 → Level 6

## Goal
Find a file in the `inhere` directory that is human-readable, 1033 bytes, and not executable.

## Solution
1. Connected to the server using SSH: 
```
ssh -p 2220 bandit5@bandit.labs.overthewire.org
```
2. Listed files in the directory:
```
ls
```
3. Found a directory named `inhere`

4. Changed directory to `inhere`:
```
cd inhere
```
5. Listed files in the `inhere`:
```
ls 
```
6. Found multiple files in the directory.

7. Used the following command to find the file with the specified properties:
```
find . -type f -size 1033c ! -perm /111
```
8. Found a file `./maybehere07/.file2` . 
9. Read the file:
```
cat ./maybehere07/.file2
```
## Result
The password for the next level was found in the file `./maybehere07/.file2`.

## Learning
- I learned how to use the `find` command to search for files and directories.
- Basic syntax: `find [path] [options] [expression]`
- 
- Useful options I learned:
  - `-name` → search by file name
  - `-type f` → search for files
  - `-type d` → search for directories
  - `-size` → search by file size:
    - `+` larger than
    - `-` smaller than
    - exact size (no sign)
    - units: `c` (bytes), `k` (KB), `M` (MB), `G` (GB)
  - `-empty` → find empty files or directories

- I learned how to use `-perm` with the `find` command to search based on file permissions.
- `-perm mode` → exact match of permissions
- `-perm -mode` → all specified permission bits must be set (AND)
- `-perm /mode` → any of the specified permission bits can be set (OR)
- `!` → negates the condition (NOT)
