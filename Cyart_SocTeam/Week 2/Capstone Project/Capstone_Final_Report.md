CAPSTONE PROJECT - FULL ALERT-TO-RESPONSE CYCLE



1.EXECUTIVE SUMMARY

On 2026-03-19, a full-cycle attack simulation was conducted against a Metasploitable2 instance. The attack involved reconnaissance, exploitation of the VSFTPD 2.3.4 backdoor, and successful privilege escalation to root.



2.ATTACK \& DETECTION TIMELINE

* RECONNAISSANCE: Nmap scan identified open ports 21 (FTP) and 6200 (Backdoor).
* EXPLOITATION: Metasploit "unix/ftp/vsftpd\_234\_backdoor" was executed.
* DETECTION: Wazuh SIEM, configured to monitor /var/log/auth.log, captured the intrusion.
* ALERT 5404: Detected 3 failed sudo attempts (Brute Force/Guessing).
* ALERT 5501: Detected the final successful root session (Privilege Escalation).



3.RESPONSE \& CONTAINMENT

Upon detection, the analyst implemented a network block via "iptables" on the target VM to shunt the attacker's IP. Ping tests confirmed the attacker was successfully isolated from the service.



4.RECOMMENDATION

Decommission the vulnerable VSFTPD service and transition to SFTP. Implement MFA for all sudo-level access.





