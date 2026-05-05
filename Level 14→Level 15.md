# Bandit Level 14 → Level 15

## Goal
The Password is returned after sending the current level password to `port 30000` on localhost.

## Solution

1. Connected to the server using SSH (Authentication was done using a private key in the previous level): 
```
ssh -p 2220 bandit14@bandit.labs.overthewire.org
```
2. Used `nc` (Netcat) to communicate with the server, and piped the password using `echo` to send it directly:
```
echo "MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS" | nc 127.0.0.1 30000
```

## Result
The password for the next level was returned by the server after submitting the current password.

## Learning
- I learned that `Netcat` can be used to establish a connection to a server and send/receive data.
- Basic syntax:
  - `nc [host] [port]`
