Task-3: Web Application Security Testing (DVWA)
Objective

The objective of this task was to identify and demonstrate common web application vulnerabilities using Damn Vulnerable Web Application (DVWA). The testing was performed in a controlled lab environment using Kali Linux and security tools such as Burp Suite.

Lab Environment

Attacker Machine: Kali Linux
Target Application: DVWA (Damn Vulnerable Web Application)
Web Server: Apache
Database: MariaDB
Tools Used:

Burp Suite

Browser Developer Tools

cURL

Manual testing

DVWA security level was set to Low to simulate vulnerable conditions.

Attack Scenarios and Findings
1. SQL Injection

Attack Scenario

The application allows user input to be directly included in SQL queries without proper validation.

Payload used:

1' OR '1'='1

Result

The application returned all user records from the database.

Impact

Database data exposure

Authentication bypass

Unauthorized data modification

Mitigation

Use prepared statements / parameterized queries

Implement proper input validation

Use ORM frameworks

2. Stored Cross-Site Scripting (Stored XSS)

Attack Scenario

A malicious script was inserted into the application input field.

Payload:

<script>alert('Stored XSS')</script>

Result

The script executed when the page loaded.

Impact

Session hijacking

Cookie theft

Malicious script execution in user browsers

Mitigation

Sanitize user input

Encode output properly

Implement Content Security Policy (CSP)

3. Reflected Cross-Site Scripting (Reflected XSS)

Attack Scenario

User input was reflected in the response without validation.

Payload:

<script>alert('Reflected XSS')</script>

Result

JavaScript executed in the browser.

Impact

Phishing attacks

Session theft

Malicious redirects

Mitigation

Validate and sanitize user inputs

Encode output before rendering

Implement CSP headers

4. Local File Inclusion (LFI)

Attack Scenario

The application includes files using user-controlled input.

Example payload:

?page=../../../../var/www/html/DVWA/index.php

Result

The server included unauthorized files.

Impact

Access to sensitive files

Potential remote code execution

Mitigation

Restrict file paths

Use whitelisting for allowed files

Disable unnecessary PHP functions

5. Cross-Site Request Forgery (CSRF)

Attack Scenario

The password change functionality did not verify request authenticity.

Result

Password was changed without verifying the user's intent.

Impact

Unauthorized account actions

Privilege misuse

Mitigation

Implement CSRF tokens

Validate request origin

Use secure session management

6. HTTP Request Interception (Burp Suite)

Burp Suite was used to intercept HTTP requests between the client and server.

Captured request example:

POST /DVWA/login.php
username=admin&password=password

Impact

Attackers can manipulate parameters

Sensitive data exposure

Mitigation

Use HTTPS encryption

Implement secure authentication mechanisms

Validate server-side inputs

7. Security Headers Analysis

HTTP headers were analyzed using:

curl -I http://localhost/DVWA

Observation

Important security headers were missing:

Content-Security-Policy

X-Frame-Options

X-Content-Type-Options

Mitigation

Implement security headers such as:

Content-Security-Policy
X-Frame-Options
X-Content-Type-Options
Strict-Transport-Security

Conclusion
The testing demonstrated multiple common web application vulnerabilities in the DVWA environment. These vulnerabilities highlight the importance of secure coding practices, input validation, and proper security configurations.
Implementing secure development practices and security controls can significantly reduce the risk of exploitation.
