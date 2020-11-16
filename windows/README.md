# Window Enumeration

## Recon

### Ping
```
ttl=127
```

- A TTL of 127 signifies that it is a Windows box, because the default TTL for packets is 128.
  - Linux has a default of 64.
  - Cisco routers have a default of 255.

### nmap
```
nmap -v -sC -sV -oA nmap/forest 10.10.10.161
sleep 300; nmap -p- -oA nmap/forest-all 10.10.10.161
```

### SMB (File shares)
```
smbclient -L <ip>
```

### DNS

#### Leak hostname
```
$ nslookup
> server <server ip>    // configure to use box as server
> 127.0.0.1
> 127.0.0.2
> <server ip>
```

### Active directory
```
```
