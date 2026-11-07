# Hack The Box - Starting Point | Tier 0

SOC Analyst Journey - Hands-on Penetration Testing Practice

## 👤 About Me
BCA Student | Aspiring SOC Analyst | Learning by Hacking Real Machines

## 🎯 What I Did - Tier 0 (4/4 Pwned)
| Machine | Port | Service | Vulnerability | Access |
| --- | --- | --- | --- | --- |
| Meow | 23 | Telnet | Weak / Blank Password | root |
| Fawn | 21 | FTP | Anonymous Login | anonymous |
| Dancing | 445 | SMB | Open Share | Guest |
| Redeemer | 6379 | Redis | No Auth, Exposed DB | No Auth |

## 🛠️ Tools & Skills Used
- Nmap - Port Scanning, Service Enumeration, Version Detection
- Telnet, FTP, SMBClient, Redis-CLI
- Linux CLI - ls, cat, get, cd, select, keys
- Methodology - Recon -> Enumeration -> Exploitation -> Flag Extraction

## 🔍 SOC Relevance - What I Learned for SOC
- **Telnet (23):** Clear-text credentials - Must be replaced with SSH (22)
- **FTP (21):** Anonymous Login allows data theft - Must use SFTP
- **SMB (445):** Open Shares lead to lateral movement - Must restrict permissions, monitor for EternalBlue / WannaCry patterns
- **Redis (6379):** Unauthenticated DB exposure - Must enable AUTH, bind to localhost, block internet exposure

## 📁 Structure
- 01-Meow-Telnet.md
- 02-Fawn-FTP.md
- 03-Dancing-SMB.md
- 04-Redeemer-Redis.md

> All flags are intentionally omitted as per HTB policy. Only methodology and remediation are documented.
