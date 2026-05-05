# Bandit Level 15 → Level 16

## Goal
The Password is retrieved by submitting the current level password to localhost on port 30001 using SSL/TLS encryption.

## Solution

1. Connected to the server using SSH : 
```
ssh -p 2220 bandit15@bandit.labs.overthewire.org
```
2. Used `ncat` to communicate with the server, and piped the password using `echo` to send it directly:
```
echo "8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo" | ncat --ssl 127.0.0.1 30001
```

## Result
The password for the next level was returned by the server after submitting the current password.

## Learning
- I learned that `ncat` is a network communication tool and an enhanced version of `nc`, as it supports encryption and additional features.
  - Basic syntax:
  - `ncat --ssl [host] [port]`
