# SOC Operations: Advanced Log Analysis & Incident Response

### Project Overview
This project simulates a full-lifecycle defense strategy within a SOC environment. It utilizes the ELK Stack, Linux Audit Framework (auditd), and Python-based automation to detect and neutralize a multi-stage attack involving brute-force attempts, DNS exfiltration, and unauthorized file access.

### Core Security Pillars
* Advanced Log Analysis: Enhances monitoring through correlation, anomaly detection, and log enrichment to identify complex patterns.
* Threat Intelligence Integration: Incorporates global threat data to understand attacker behavior and prioritize responses.
* Incident Escalation Workflows: Defines structured paths for alert prioritization and communication (SITREPs) across tiered SOC levels.
* SOAR Principles: Implements Security Orchestration, Automation, and Response to minimize the Mean Time to Respond (MTTR).

### Technical Implementation Phases

**Phase 1: Detection & Correlation**
The objective was to link seemingly unrelated events to reveal a multi-stage attack.
* Brute-Force Identification: Detected ~3,000 failed login attempts (Event Code 4625) targeting accounts like admin and root from IP 192.168.1.50.
* Pivot to Network Traffic: Correlated the source IP with ~2,000 network events, suggesting outbound data exfiltration.
* Threshold-Based Alerts: Configured a rule to trigger high-severity alerts for DNS exfiltration exceeding 1 MB.

**Phase 2: Threat Intelligence & IoC Matching**
This phase shifted the focus from behavior to identity-based detection.
* Indicator Validation: Cross-checked internal IoCs against global databases like VirusTotal to determine reputation.
* Automated Indicator Matching: Implemented rules in Elastic Security to compare real-time traffic against known-malicious IP indices.
* Alert Generation: Successfully generated 100+ "Threat Intelligence Match" alerts for blacklisted IP communication.

**Phase 3: Endpoint Security (FIM)**
To confirm a breach, File Integrity Monitoring was established at the kernel level.
* The Honey-File Trap: Created /tmp/confidential_db.txt to act as a "tripwire" for unauthorized access.
* Auditd Monitoring: Used the Linux Audit Framework to track read/write/modification attempts.
* Breach Confirmation: Captured six critical interactions where the user attacker_session used the cat command to access the honey-file.

**Phase 4: Visualization & Analytics**
A centralized dashboard was designed to provide situational awareness across the attack lifecycle.
* Credential Spraying Analysis: Visualized distributed failed login attempts across multiple users.
* DNS Tunneling Evidence: Identified high-frequency, automated outbound communication patterns.
* Decision Support: Consolidated logs to reduce the Mean Time to Detect (MTTD).

**Phase 5: Automated Response (SOAR)**
The final phase demonstrated proactive mitigation to close the incident lifecycle.
* Manual Containment: Implemented iptables "Drop" rules to block the attacker IP at the host level.
* Python-Driven Automation: Developed soar_mitigation.py to listen for SIEM alerts and execute firewall blocks automatically.
* Performance Metric: Reduced the MTTR to just 4 seconds.

### Recommended Mitigation Controls

| Phase | Control | Action |
|-------|---------|--------|
| Authentication | Account Lockout | Enforce lockouts after five failed attempts. |
| Network | Egress Filtering | Restrict DNS queries to authorized resolvers only. |
| Endpoint | FIM Alerting | Enable real-time alerts for sensitive directory access. |

### Conclusion
This workflow proves that integrating siloed data—brute-force logs, DNS traffic, and endpoint file access—creates a comprehensive defense-in-depth posture. By leveraging automation, the SOC can transition from passive monitoring to active, real-time threat neutralization.