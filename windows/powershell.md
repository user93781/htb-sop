# Powershell tips

#### Download a remote file
```powershell
IEX(New-Object Net.WebClient).downloadString(<url>)
```