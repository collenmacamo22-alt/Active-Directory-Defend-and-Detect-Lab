# Incident Response – Password Spraying

## Objective

Provide a structured response procedure for suspected password spraying attacks against Active Directory user accounts.

---

## Incident Severity

**High**

Escalate to **Critical** if:

- A successful login occurs after repeated failures.
- A privileged account is compromised.
- Multiple systems are affected.

---

## Containment

Immediately:

- Identify the affected user accounts.
- Identify the originating IP address.
- Block the source IP if confirmed malicious.
- Force password resets for compromised accounts.
- Disable compromised accounts if necessary.

---

## Investigation

The SOC analyst should determine:

- Which accounts were targeted?
- Was a successful authentication achieved?
- Which systems were accessed?
- Was administrative access obtained?
- Were additional authentication attempts observed?

---

## Eradication

If compromise is confirmed:

- Remove unauthorized access.
- Reset affected credentials.
- Review privileged group membership.
- Scan affected systems for malware or persistence mechanisms.

---

## Recovery

Before returning affected accounts to service:

- Verify account ownership.
- Confirm password changes.
- Monitor authentication activity.
- Validate that no persistence mechanisms remain.

---

## Lessons Learned

Following the incident:

- Review password policy effectiveness.
- Evaluate account lockout thresholds.
- Strengthen authentication monitoring.
- Consider implementing Multi-Factor Authentication (MFA).
- Update detection rules if necessary.
