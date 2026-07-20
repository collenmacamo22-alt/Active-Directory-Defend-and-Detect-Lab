# Brute Force Attack Against Active Directory

## Scenario

An attacker repeatedly attempts multiple passwords against a single Active Directory user account.

After several failed login attempts, the attacker successfully authenticates using the correct password.

Shortly afterward, PowerShell is launched and administrative commands begin executing.

---

## Indicators

- Multiple failed logons
- Successful authentication
- PowerShell execution
- Administrative command execution
- Activity outside business hours
- Login from an unfamiliar IP address

---

## MITRE ATT&CK

- Initial Access
- Valid Accounts
- Command and Scripting Interpreter (PowerShell)
- Execution

---

## Detection Opportunities

- Multiple failed logons followed by a successful login.
- Successful logon from unfamiliar locations.
- PowerShell launched immediately after authentication.
- Authentication outside business hours.
