# Bandit Level 16 → Level 17

## Goal
Credentials are retrieved by identifying the correct SSL/TLS service on ports 31000–32000 and submitting the current password.

## Solution

1. Connected to the server using SSH: 
```
ssh -p 2220 bandit16@bandit.labs.overthewire.org
```
2. Used `nmap` with service detection `-sV` to identify active services on ports 31000–32000 on localhost:
```
nmap -sV -p 31000-32000 127.0.0.1
```
3. Identified an SSL/TLS-enabled service on port 31790 that was actively responding.
4. Used `ncat` to establish a secure connection to the SSL/TLS service and piped the password using `echo` for submission:
```
echo "kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx" | ncat --ssl localhost 31790
```
## Result
The credentials were found and consisted of a private SSH key.

## Learning
- I learned that `nmap` is a powerful network mapping tool used for reconnaissance and analysis.
- It can be used for:
  - Host discovery
  - Port scanning
  - Service identification
  - OS detection
  - Vulnerability assessment (using scripts)
- It also supports advanced features and scripting for deeper analysis.
- Basic syntax for port scanning:
  - `nmap -p [port] [host]`
  - Example: `nmap -p 31000-32000 localhost`
