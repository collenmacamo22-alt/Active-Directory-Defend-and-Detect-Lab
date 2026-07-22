# Password Spraying Attack

## Objective

This scenario demonstrates how a password spraying attack targets multiple user accounts using a small number of commonly used passwords in an attempt to gain unauthorized access while avoiding account lockout policies.

---

## MITRE ATT&CK

**T1110.003 – Password Spraying**

---

## Scenario

An attacker attempts to authenticate to numerous Active Directory user accounts using the same commonly used password (for example, *Winter2025!*).

Instead of repeatedly attacking one account, the attacker spreads authentication attempts across many accounts to reduce the likelihood of triggering account lockout thresholds.

Eventually, one account authenticates successfully because the password matches.

---

## Indicators of Compromise (IOCs)

Possible indicators include:

- Multiple Event ID 4625 (Failed Logon) events
- Numerous usernames targeted from the same source
- Authentication attempts within a short time window
- Event ID 4624 (Successful Logon) following multiple failures
- Authentication originating from an unfamiliar workstation or IP address

---

## Detection Opportunities

A SOC analyst should look for:

- Five or more failed logons within five minutes
- One source IP targeting multiple user accounts
- Successful authentication after repeated failures
- Authentication outside normal business hours
- Authentication from unusual geographic locations (when available)

---

## Business Impact

A successful password spraying attack may result in:

- Unauthorized access to user accounts
- Access to sensitive company data
- Privilege escalation
- Lateral movement
- Domain compromise

---

## Analyst Assessment

Password spraying differs from traditional brute-force attacks because it targets many accounts with very few passwords.

This technique is designed to bypass account lockout policies while increasing the attacker's chance of finding users with weak or reused passwords.

Monitoring authentication patterns across multiple accounts is more effective than investigating individual failed logons in isolation.

---

## Related Windows Events

- Event ID 4625 – Failed Logon
- Event ID 4624 – Successful Logon
- Event ID 4672 – Special Privileges Assigned (if privileged accounts are compromised)

---

## Related Detection Rule

This attack scenario is supported by the Brute Force Detection Sigma Rule documented in the Detection Engineering project.
