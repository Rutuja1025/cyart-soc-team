INCIDENT RESPONSE REPORT: \[MOCK] PHISHING CAMPAIGN



Date: 2026-03-19

Analyst: Rutuja Utekar



1.EXECUTIVE SUMMARY

On 2026-03-19, a phishing email was reported via the "Report Phish" button.

The email impersonated "IT Support" requesting a password sync.



A.TIMELINE

* 10:00 AM: Phishing email hit 50 corporate inboxes.
* 10:15 AM: First user report received by SOC.
* 10:20 AM: URL analyzed and confirmed malicious (60/90 on VirusTotal).
* 10:45 AM: Malicious domain blocked at DNS level.



B.IMPACT ANALYSIS

* Scope: 50 users received the email.
* Compromise: 2 users clicked the link; credentials suspected compromised.



C.REMEDIATION STEPS

* Blocked domain: it-support-portal-sync.xyz at the firewall.
* Triggered forced password reset for identified clicking users.
* Purged email from all O365 mailboxes.



D.LESSONS LEARNED

The attacker used a newly registered domain.

Recommendation: Implement a policy to flag or block all domains registered in the last 30 days.

