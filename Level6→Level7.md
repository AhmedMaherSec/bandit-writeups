# Bandit Level 5 → Level 6

## Goal
Find the password in a file on the server owned by bandit7, group bandit6, and 33 bytes in size.

## Solution
1. Connected to the server using SSH: 
```
ssh -p 2220 bandit6@bandit.labs.overthewire.org
```
2. Changed directory to root directory`:
```
cd /
```
3. Used the following command to find the file with the specified properties:
```
find . -size 33c -type f -user bandit7 -group bandit6
```
4. The search returned many files, along with multiple "Permission denied" errors. 
5. Ignored the "Permission denied" errors:
```
find . -size 33c -type f -user bandit7 -group bandit6 2>/dev/null
```
6. Found a file `./var/lib/dpkg/info/bandit7.password`
7. Read the file:
```
cat ./var/lib/dpkg/info/bandit7.password 
```

## Result
The password for the next level was found in the file `./var/lib/dpkg/info/bandit7.password`.

## Learning
- I learned how to use `-user` and `-group` options with the `find` command.
  - `-user` → find files owned by a specific user
  - `-group` → find files belonging to a specific group
- I learned that `2>/dev/null` redirects error messages to `/dev/null`, which helps keep the output clean.
