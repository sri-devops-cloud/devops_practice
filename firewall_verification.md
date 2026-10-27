# Firewall Verification

## Objective
To check firewall rules, block a port, verify access is denied, and re-enable access.

## Procedure

1. Checked the current Windows Firewall status using PowerShell.
2. Viewed the existing firewall rules.
3. Created a rule to block inbound TCP port 8080.
4. Tested connectivity using the `Test-NetConnection` command.
5. Verified that access to the port was denied while the blocking rule was active.
6. Disabled the blocking rule and tested connectivity again.
7. Removed the temporary firewall rule after completing the test.

## Commands Used

```powershell
Get-NetFirewallProfile

Get-NetFirewallRule |
Select-Object DisplayName, Enabled, Direction, Action

New-NetFirewallRule -DisplayName "Block-Test-TCP-8080" -Direction Inbound -Protocol TCP -LocalPort 8080 -Action Block -Enabled True

Test-NetConnection 192.168.1.100 -Port 8080

Disable-NetFirewallRule -DisplayName "Block-Test-TCP-8080"

Remove-NetFirewallRule -DisplayName "Block-Test-TCP-8080"
```

## Expected Result

- Firewall status and rules were displayed.
- TCP port 8080 was blocked by a firewall rule.
- The connection test failed while access was blocked.
- The blocking rule was disabled to restore access, subject to service availability and other network rules.
- The temporary rule was removed after testing.

## Conclusion

Successfully performed firewall verification by checking firewall rules, blocking a TCP port, testing network access, and disabling the blocking rule. Documented the procedure for GitHub submission.