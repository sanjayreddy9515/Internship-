Task-2: Network Security & Scanning

Objective
The objective of this task was to perform reconnaissance, port scanning, service detection, vulnerability assessment, packet analysis, and firewall configuration in a controlled virtual lab environment.

Lab Environment
Attacker Machine: Kali Linux
Target Machine: Metasploitable 2
Network Type: Host-Only Adapter
Tools Used: Nmap, Wireshark, iptables
1. Reconnaissance
Host discovery was performed to confirm that the target system was active and reachable.

Command used: nmap -sn

The target machine was found to be up and responding.

2. Port & Service Scanning
Basic TCP Scan: nmap

The scan identified multiple open ports such as:

21 (FTP)
22 (SSH)
23 (Telnet)
80 (HTTP)
3306 (MySQL)
Service Version Detection: nmap -sV

This revealed service versions running on the open ports.

OS Detection: nmap -O

The system was identified as a Linux-based operating system.

3. Vulnerability Assessment
Vulnerability scanning was performed using Nmap NSE scripts.

Command used: nmap -sS -sV -O --script vuln

The scan detected several vulnerabilities due to outdated services and insecure configurations. The results indicate that the target machine has a large attack surface and contains known security weaknesses.

4. Packet Analysis (Wireshark)
Network traffic was captured using Wireshark.

ICMP packets observed during ping.
FTP login credentials were visible in plaintext.
HTTP requests were captured.
SYN packets observed during Nmap scanning.
This demonstrates how unencrypted protocols expose sensitive data.

5. Firewall Demonstration
A firewall rule was implemented using iptables to block outgoing HTTP traffic.

Command used: sudo iptables -A OUTPUT -p tcp --dport 80 -j DROP

After applying the rule, Nmap scans showed changes in port accessibility.

Firewall rules were cleared using: sudo iptables -F

Conclusion
This task provided practical experience in reconnaissance, scanning, vulnerability detection, traffic analysis, and firewall configuration. The results highlight the importance of securing open services, updating software, and implementing proper firewall rules to reduce security risks.
