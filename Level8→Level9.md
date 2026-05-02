# Bandit Level 8 → Level 9

## Goal
The password is the only line in `data.txt` that appears exactly once.

## Solution
1. Connected to the server using SSH: 
```
ssh -p 2220 bandit8@bandit.labs.overthewire.org
```
2. Listed files in the directory:
```
ls
```
3. Found a file named `data.txt`
4. Searched for the unique line that does not repeat in the `data.txt` :
```
sort data.txt | uniq -u
```

## Result
The password is in the line that appears only once in the file.

## Learning
- I learned that the `uniq` command is used to remove or handle duplicate lines in a file.
--`uniq` (without options) → removes adjacent duplicate lines.
--`uniq -u` → shows only unique (non-repeated) lines.
--`uniq -d` → shows only duplicate lines.
--`uniq -c` → displays the number of occurrences of each line.

- I learned that `uniq` works properly only on sorted data, because it compares only adjacent lines. Therefore, it is usually used with the `sort` command.
--`sort` (without options) → sorts lines in a file in ascending order.
