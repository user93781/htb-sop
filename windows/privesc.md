# Privilege Escalation on Windows

## Finding vectors

#### List all administrators
```cmd
net localgroup Administrators
```

#### Determine groups a user is a member of
```cmd
net user <user>
net user Administrator
```

### JAWS
- "Just Another Windows enumeration Script"

## References
- https://eaneatfruit.github.io/2019/08/18/Offensive-Lateral-Movement/