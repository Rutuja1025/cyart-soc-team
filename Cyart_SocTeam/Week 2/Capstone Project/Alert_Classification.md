ALERT CLASSIFICATION SYSTEM

+----------+----------------------+------------+----------------------+-----------------+

| ALERT ID | TYPE | PRIORITY | MITRE TACTIC | MITRE TECHNIQUE |

+----------+----------------------+------------+----------------------+-----------------+

| 5404 | Failed Sudo Attempts | High (10) | Privilege Escalation | T1548.003 |

| 5501 | Successful Root Login| Low (3)\* | Initial Access | T1078 |

| 5712 | SSH/FTP Auth Failure | High (10) | Credential Access | T1110 |

+----------+----------------------+------------+----------------------+-----------------+

NOTES:

Rule 5501 is Level 3 by default, but in a SOC triage, it is elevated to

Critical when it follows a Level 10 exploit attempt.

COMPLIANCE MAPPING:

GDPR: IV\_32.2

HIPAA: 164.312.b

PCI\_DSS: 10.2.5

================================================================================

