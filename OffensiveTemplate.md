# Red Team: Summary of Operations

## Table of Contents
- Exposed Services
- Critical Vulnerabilities
- Exploitation

### Exposed Services
_TODO: Fill out the information below._

Nmap scan results for each machine reveal the below services and OS details:

```bash
$ nmap -sC -sV 192.168.1.110
  22/tcp open ssh
  80/tcp open http
  11/tcp open rpcbind
  139/tcp open
  445/tcp open
```

This scan identifies the services below as potential points of entry:
- Target 1
  - Port 80
  - Port 22

_TODO: Fill out the list below. Include severity, and CVE numbers, if possible._

The following vulnerabilities were identified on each target:
- Target 1
  - Username Enumeration
  - Using Unsalted Hash
  - Root Privilege Escalation

_TODO: Include vulnerability scan results to prove the identified vulnerabilities._

### Exploitation
_TODO: Fill out the details below. Include screenshots where possible._

The Red Team was able to penetrate `Target 1` and retrieve the following confidential data:
- Target 1
  - `flag1.txt`: {b9bbcb33e11b80be759c4e844862482d}
    - **Exploit Used**
      - I used port 22 (ssh) to michael's account and found the flag1 in a file.
      - ssh michael@192.168.1.110
  - `flag2.txt`: {fc3fd58dcdad9ab23faca6e9a36e581c}
    - **Exploit Used**
      - i found flag 2 in michael's account, inside /var/www/
      - cat /var/www/flag2.txt
