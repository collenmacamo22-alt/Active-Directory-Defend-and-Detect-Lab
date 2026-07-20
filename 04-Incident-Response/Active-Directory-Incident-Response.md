# Active Directory Incident Response

## Initial Response

Upon receiving an alert indicating possible Active Directory compromise:

1. Validate the alert.
2. Identify the affected user account.
3. Determine the source IP address.
4. Review authentication history.

---

## Containment

- Disable or lock the compromised account.
- Isolate affected systems if malicious activity is confirmed.
- Block malicious IP addresses when appropriate.
- Preserve logs and evidence before making major changes.

---

## Investigation

Review:

- Windows Security Event Logs
- Process Creation Events
- PowerShell activity
- Authentication history
- Group membership changes
- Privilege escalation attempts

---

## Recovery

- Reset compromised credentials.
- Re-enable accounts after validation.
- Remove attacker persistence.
- Confirm normal authentication behavior has resumed.

---

## Lessons

Early detection significantly reduces attacker dwell time.

Event correlation provides much higher confidence than isolated alerts.
