# Initial Accses

## Gathering credentials

### Password cracking

#### Hashcat

```bash
hashcat --status -o <out file> -m <hash type> -a <attack mode> <hashes>.txt <wordlist>.txt
```

### Windows NTLM hash dump

```bash
impacket-secretsdump
```

- `31d6cfe...` for NT hash means that the hash is blanked out (i.e. not a
  valid hash). Usually means that the account is disabled.

##### Attack modes
- `0`: straight (simple word list attack)
- `1`: combination
- `3`: bruteforce
- `6`: hybrid wordlist + mask
- `7`: hybrid mask + wordlist

##### Common hash types
- `md5`: `0`
- `sha256`: `1400`

## `.scf` file exploit

## Pass the hash

### `smbmap`

```bash
# Find shares that can be accessed with the hash
smbmap -u <username> -p <NTLM hash> -H <host>
```

#### Flags
- `-R`: Recursively list permissions.
- `--download <file path>`: Download a file.

## Discovering exploits

### `searchsploit`
- `searchsploit "<app name>"`
- `searchsploit -x <exploit id>`

#### Flags
- `-x`. Examine a specific exploit.

### `sqlmap`


#### Flags
- `-r <request file>`: load a HTTP request format from a file.
- `--risk (1|2|3)`: risk (1-3) of tests to perform.
- `--level`: level (1-5) of tests to perform