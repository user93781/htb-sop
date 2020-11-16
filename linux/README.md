# Linux

## General tips
- Accessing a website may require adding entries into the `/etc/hosts` file.

---

## Reconnaissance

### Port scanning
- `nmap -p -T3 <ip> -oA initial-scan`

### Web directory scanning
- `gobuster dir -u <url> -w <wordlist>`

---

## Password cracking

### Hashcat

```bash
hashcat --status -o <out file> -m <hash type> -a <attack mode> <hashes>.txt <wordlist>.txt
```

#### Attack modes
- `0`: straight (simple word list attack)
- `1`: combination
- `3`: bruteforce
- `6`: hybrid wordlist + mask
- `7`: hybrid mask + wordlist

#### Common hash types
- `md5`: `0`
- `sha256`: `1400`

---

## Metasploit

### Set the payload
- `set payload <payload>`

#### Common payloads
- `php/meterpreter/bind_tcp`

---

## Privilege Escalation
- Look at the running processes (`ps aux`).
