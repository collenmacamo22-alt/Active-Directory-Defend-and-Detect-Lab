# Authentication Detection Logic

## Detection Rule

Generate a High severity alert when:

- Five or more failed logon attempts occur against the same account.
- The attempts occur within five minutes.
- A successful logon immediately follows.

Increase severity to Critical if:

- The source IP is unfamiliar.
- The authentication occurs outside business hours.
- The account belongs to Domain Admins or another privileged group.

---

## Windows Event IDs

| Event ID | Description |
|----------|-------------|
| 4624 | Successful Logon |
| 4625 | Failed Logon |
| 4672 | Special Privileges Assigned |
| 4688 | Process Creation |
