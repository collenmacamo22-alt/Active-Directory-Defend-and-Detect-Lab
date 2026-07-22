# Detection Logic – Privilege Escalation

## Detection Objective

Detect attempts to gain or abuse elevated privileges by identifying unusual administrative logons, privileged account activity, and suspicious process execution.

---

## Detection Strategy

Privilege escalation is rarely identified by a single event.

Detection should correlate authentication events, privilege assignment, and subsequent administrative activity to determine whether elevated privileges are being abused.

---

## Windows Events

Primary Events:

- Event ID 4624 – Successful Logon
- Event ID 4672 – Special Privileges Assigned

Supporting Events:

- Event ID 4688 – Process Creation
- Event ID 4625 – Failed Logon (if privilege escalation follows repeated authentication attempts)

---

## Detection Conditions

Generate a High Severity Alert if:

- A privileged account logs in outside business hours.
- Event ID 4672 is generated for an unexpected account.
- Administrative tools (PowerShell, cmd.exe, certutil.exe) execute shortly after authentication.
- Administrative activity originates from an unfamiliar workstation.

Escalate the alert to Critical if:

- Windows Defender or other security controls are disabled.
- New privileged accounts are created.
- Multiple systems show similar privileged activity.
- Evidence of lateral movement is observed.

---

## False Positives

Possible legitimate causes include:

- Scheduled maintenance.
- System administrators performing approved work.
- Software deployment activities.
- Security team administrative tasks.

These activities should be verified against maintenance schedules and change management records.

---

## Analyst Response

Upon receiving this alert, the SOC analyst should:

1. Verify the identity of the privileged account.
2. Confirm whether the activity was authorized.
3. Review authentication history for the account.
4. Examine processes started after the privileged logon.
5. Investigate whether security settings were modified.
6. Isolate affected systems if malicious activity is confirmed.
