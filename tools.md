# Tools and utilities

## `find`
- `find / -type f -perm -4000 -exec ls -l {} \;`

## `locate`
- `locate -r <regex string>`
    - `locate -r $nse$` (find all nmap scripts)

## `putty-tools`
- `sudo apt-get install putty-tools`

### `puttygen`

Key generator and converter for PuTTY tools.

## `guestmount` (`libguestfs-tools`)

```bash
guestmount -v --add <vhd file> --inspector --ro <mount path>
```

## `7z`
- `7z` can read `.vhd` (virtual hard disk) files.

## Mounting SMB file shares

```bash
mount -t cifs //<host or ip>/<share name>
```

## Output formatting
- `column`


## `xclip`