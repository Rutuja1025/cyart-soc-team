# Week 2: SOC Team Operations & Practical Application
**Analyst:** Rutuja Utekar  
**Date:** March 19, 2026  
**Tools Used:** Wazuh SIEM, Metasploit Framework, Kali Linux, Metasploitable2, AlienVault OTX.

---

## Project Overview
This repository contains the documentation and technical evidence for the Week 2 SOC Analyst lab. The project covers the full lifecycle of a security incident: from classification and triage to active defense and evidence preservation.

---

## Step-by-Step Practical Execution

### Task 1: Alert Management Practice
1. **Configuration:** Modified `/var/ossec/etc/ossec.conf` on the Wazuh Manager to monitor critical system logs (`/var/log/auth.log` and `/var/log/syslog`).
2. **Classification:** Created a mapping system in `Alert_Classification.md` linking Wazuh Rule IDs (e.g., 5404, 5501) to **MITRE ATT&CK** tactics like *Privilege Escalation* and *Credential Access*.
3. **Visualization:** Developed a custom **Wazuh Dashboard Pie Chart** to visualize alert priorities (Critical vs. High vs. Medium).

### Task 2: Response Documentation
1. **Standardization:** Adopted the **SANS Incident Response Template** to document a simulated Phishing attack.
2. **Checklists:** Created a technical `Phishing_Checklist.md` to ensure consistent triage (Header analysis, URL reputation checks, and containment).

### Task 3: Alert Triage Practice
1. **Simulation:** Triggered multiple failed `sudo` attempts on the Kali endpoint to generate high-severity alerts.
2. **Validation:** Investigated **Alert 5404** (Sudo failure) and **Alert 5501** (Session Opened).
3. **Threat Intel:** Cross-referenced internal IP activity with **AlienVault OTX** to validate Indicators of Compromise (IOCs).

### Task 4: Evidence Preservation
1. **Volatile Data Collection:** Captured real-time network connections using the `ss -tunap` utility, saving the output to `netstat_evidence.txt`.
2. **Chain of Custody:** Generated **SHA256 hashes** for all collected evidence immediately after acquisition to ensure data integrity.
3. **Logging:** Documented all evidence items in `Evidence_Log.md` with timestamps and analyst signatures.

### Task 5: Capstone - Full Alert-to-Response Cycle
1. **Attack:** Executed the `vsftpd_234_backdoor` exploit via **Metasploit** against a Metasploitable2 target (192.168.0.114).
2. **Detection:** Verified that Wazuh successfully flagged the **T1078 (Valid Accounts)** and **T1190 (Exploit Public-Facing Application)** techniques.
3. **Containment:** Manually updated `iptables` rules on the target VM to drop all traffic from the attacker's IP.
4. **Reporting:** Drafted a 200-word technical report and a 100-word stakeholder briefing.

---