# PowerShell Remote

https://www.faqforge.com/windows/create-powershell-session-remote-computer

1. On remote: `Enable-PSRemoting -Force` as admin
2. On both: `winrm set winrm/config/client '@{TrustedHosts="*"}`
3. On both? `Restart-Service WinRM`
4. On local: `Test-WsMan NUC`

```powershell
$credentials = Get-Credential
$session = New-PSSession -Credential $credentials -ComputerName NUC
Enter-PSSession $session
# Commands…
Exit-PSSession
Remove-PSSession $session
```

## To-Do

### Configure this on the personal computer and the home server

### Look into using specific computer names in `TrustedHosts`

To lock things down a bit just in case.
