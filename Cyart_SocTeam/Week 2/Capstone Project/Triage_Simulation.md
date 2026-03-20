ALERT TRIAGE REPORT

ANALYST: Rutuja Utekar



INCIDENT ID: 1773915921.101210



FINDINGS:

The investigation focused on Alert 5501 (PAM Session Opened). Logs from /var/log/auth.log show that user "kali" successfully opened a session for root(uid=0).



THREAT INTELLIGENCE VALIDATION:

* SOURCE: Internal Host (kali)
* STATUS: True Positive
* CONTEXT: This session was opened immediately following multiple failed sudo attempts (Rule 5404). This sequence indicates a successful Privilege Escalation (T1548.003) via the Metasploit VSFTPD backdoor exploit.
