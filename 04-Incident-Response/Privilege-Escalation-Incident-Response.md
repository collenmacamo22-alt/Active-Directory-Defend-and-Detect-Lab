# Incident Response – Privilege Escalation

## Objective

Provide a structured response procedure for suspected privilege escalation activity within an Active Directory environment.

---

## Incident Severity

**Critical**

Privilege escalation attempts have the potential to compromise administrative accounts, security controls, and the overall integrity of the Active Directory environment.

---

## Initial Response

Immediately:

- Verify the identity of the affected account.
- Determine whether the privileged activity was authorized.
- Notify the incident response team.
- Begin collecting relevant security logs.

---

## Containment

If malicious activity is confirmed:

- Disable or suspend the compromised account.
- Isolate affected systems from the network.
- Prevent additional privileged logons.
- Preserve evidence before making significant system changes.

---

## Investigation

The SOC analyst should determine:

- How were elevated privileges obtained?
- Which accounts were affected?
- Which systems were accessed?
- Were new administrator accounts created?
- Were security settings or Group Policy modified?
- Was lateral movement attempted?

---

## Eradication

After identifying the root cause:

- Remove unauthorized accounts.
- Revoke unnecessary privileges.
- Remove malicious tools or persistence mechanisms.
- Restore modified security settings.

---

## Recovery

Before returning systems to production:

- Verify Active Directory integrity.
- Reset compromised credentials.
- Confirm privileged group memberships.
- Monitor privileged authentication activity closely.

---

## Lessons Learned

Following the incident:

- Review privileged access policies.
- Strengthen monitoring for Event IDs 4624, 4672, and 4688.
- Implement least privilege where possible.
- Update detection rules based on investigation findings.
- Conduct a post-incident review with the security team.
