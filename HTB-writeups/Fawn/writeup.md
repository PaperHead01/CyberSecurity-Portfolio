# HackTheBox Writeup — Fawn

## Machine Information
Name: Fawn  
Difficulty: Very Easy  
OS: Linux  
Target IP: 10.129.7.229  

---

## Objective
Gain access to the target machine and retrieve the flag.

---

## Step 1 — Connectivity Check

Verify that the target machine is reachable.

Command:
ping 10.129.7.229

---

## Step 2 — Port Scanning

Scan for open ports and services.

Command:
nmap -sC -sV 10.129.7.229

Explanation:
-sC → default scripts  
-sV → service version detection  

Result:
PORT   STATE SERVICE VERSION
21/tcp open  ftp     vsftpd 3.0.3

Observation:
FTP service is running on port 21.

---

## Step 3 — Service Enumeration

Since FTP is open, attempt connection.

Command:
ftp 10.129.7.229

---

## Step 4 — Exploitation

Login using anonymous access.

Username:
anonymous  

Password:
(blank)

Login successful.

Observation:
FTP allows anonymous login without authentication.

---

## Step 5 — File Enumeration

List files in the directory.

Command:
ls

A file named flag.txt is found.

---

## Step 6 — Downloading the Flag

Download the file.

Command:
get flag.txt

Verify locally:

cat flag.txt

Flag successfully retrieved.

---

## Vulnerability Analysis

The FTP server allows anonymous login.

Security Issues:
• Unauthorized access to files  
• No authentication required  
• Sensitive data exposure  

---

## Mitigation

• Disable anonymous FTP login  
• Restrict access with authentication  
• Use secure protocols like SFTP  

---

## Lessons Learned

• Always check for anonymous FTP access  
• Enumeration is key in penetration testing  
• FTP is insecure and should be avoided
