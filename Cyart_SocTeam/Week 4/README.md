Security Operations Center (SOC) Project



Project Overview

This project demonstrates the implementation of a Security Operations Center (SOC) workflow focused on threat detection, monitoring, and automated incident response. It simulates real-world attack scenarios and showcases how security tools and methodologies work together to identify and mitigate threats in real time.



Key Features

Proactive threat hunting using hypothesis-driven analysis

Centralized log collection and monitoring

Real-time event correlation and anomaly detection

Endpoint monitoring with file integrity tracking

Automated incident response using SOAR principles

Security posture assessment using industry benchmarks



Tools and Technologies

Wazuh (SIEM \& Endpoint Monitoring)

Kali Linux (Attacker Machine)

Windows 10 (Target System)

MITRE ATT\&CK Framework

Metasploit (Post-Exploitation)

Elastic Stack (Log Analysis)



Project Workflow



Phase 1 Post-Exploitation Analysis

Analyzed attacker behavior after system compromise. Privilege escalation attempts failed due to security controls, but keylogging and screen capture were successfully executed, highlighting data exposure risks.



Phase 2 Endpoint Monitoring

Deployed Wazuh agent and established secure communication with the SIEM. Conducted security configuration assessment, identifying multiple system vulnerabilities and weak configurations.



Phase 3 Log Analysis

Collected and analyzed system logs to establish baseline behavior. Verified SIEM capabilities including anomaly detection, network monitoring, and event correlation.



Phase 4 Automated Incident Response

Simulated brute-force attack detected via failed login events. Automated response successfully blocked attacker IP, reducing response time significantly.



Key Outcomes

Improved visibility across endpoint and network activity

Early detection of suspicious behavior

Automated threat containment

Reduced Mean Time to Detect (MTTD) and Respond (MTTR)



Conclusion

This project highlights how integrating monitoring, detection, and automation enables a strong defense-in-depth strategy. It demonstrates the transition from passive monitoring to active threat response, improving overall SOC efficiency and security posture.

