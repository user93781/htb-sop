# Enumeration

---

## ping
```
64 bytes from 127.0.0.1: icmp_seq=1 ttl=64 time=0.059 ms
```

- A TTL of 127 signifies that it is a Windows box, because the default TTL for packets is 128.
  - Linux has a default of 64.
  - Cisco routers have a default of 255.

---

## nmap
```bash
# scan common ports and use default scripts, scan for versions
nmap -v -sC -sV -oA nmap/<prefix> <ip>

# scan all ports to see if any are open
sleep 300; nmap -p- -oA nmap/<prefix>-all <ip>
```

---

## SMB (File shares)
```bash
smbclient -L <ip>
```

---

## DNS

### Leak hostname
```
$ nslookup
> server <server ip>    // configure to use box as server
> 127.0.0.1
> 127.0.0.2
> <server ip>
```

---

## Active directory
```bash
ldapsearch -x -h <host> -s <scope>
```

- Flags
  - `-x`: simple authentication
    - provide _distinguished name (DN)_ and _password_
  - `-s`: scope
    - `base`
    - `sub`: whole subtree.

```bash
nmap -p 389 --script ldap-rootdse -Pn <host>
nmap -p 389 --script ldap-search -Pn <host>
```

---

## SSH

### Finding users with SSH and metasploit
```
$ msfconsole
> use auxiliary/scanner/ssh/ssh_enumusers
```

---

## Web

### Web directory scanning
- `gobuster dir -u <url> -w <wordlist>`