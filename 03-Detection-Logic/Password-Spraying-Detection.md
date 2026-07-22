# Detection Logic – Password Spraying

## Detection Objective

Detect password spraying attacks by identifying authentication patterns that indicate an attacker is attempting to compromise multiple accounts using a small number of common passwords.

---

## Detection Strategy

Rather than investigating individual failed logons, the detection logic correlates authentication events over a short period of time.

The goal is to identify abnormal authentication behavior that would not typically occur during normal user activity.

---

## Windows Events

Primary Events:

- Event ID 4625 – Failed Logon
- Event ID 4624 – Successful Logon

Supporting Events:

- Event ID 4672 – Special Privileges Assigned (if privileged accounts are involved)

---

## Detection Conditions

Generate a High Severity Alert if:

- Five or more failed logons occur within five minutes.
- Multiple user accounts are targeted.
- Authentication attempts originate from the same source.
- A successful authentication follows repeated failures.

Escalate the alert to Critical if:

- Authentication originates from an unfamiliar IP address.
- Authentication originates from another country.
- The successful login occurs outside business hours.
- The compromised account receives administrative privileges.

---

## False Positives

Possible legitimate causes include:

- Users repeatedly entering incorrect passwords.
- Password expiration events.
- Help desk password testing.
- Authentication testing performed by administrators.

These situations should be validated before escalating the incident.

---

## Analyst Response

Upon receiving this alert, the SOC analyst should:

1. Identify the targeted accounts.
2. Determine the originating IP address.
3. Verify whether a successful authentication occurred.
4. Determine whether privileged accounts were affected.
5. Investigate any activity performed after successful authentication.
