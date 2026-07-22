# Lessons Learned

## Technical Lessons

Throughout this project, several important Active Directory security concepts were reinforced.

Authentication events should never be evaluated individually. Correlating multiple Windows Security Events provides significantly more context and improves detection accuracy.

Privilege assignment events become meaningful when analyzed together with authentication activity and process execution.

Successful security monitoring relies not only on collecting logs but also on ensuring that the correct auditing policies are enabled.

---

## Detection Lessons

Effective detection requires understanding attacker behavior rather than relying solely on individual Event IDs.

Password spraying, privilege escalation, and lateral movement each generate different event patterns that become much more valuable when correlated together.

Behavior-based detections are generally more reliable than detections based on single events.

---

## Incident Response Lessons

Rapid containment reduces the likelihood of privilege escalation and lateral movement.

Evidence should always be preserved before making major changes to affected systems.

Incident response should follow a structured process including identification, containment, eradication, recovery, and post-incident review.

---

## Personal Reflection

This project strengthened my understanding of Active Directory security monitoring, Windows Event analysis, detection engineering, and incident response.

It also reinforced the importance of documenting investigations clearly so that security teams can quickly understand the nature of an incident and respond effectively.
