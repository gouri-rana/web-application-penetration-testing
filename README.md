# web-application-penetration-testing
Ethical web application penetration testing assessment covering reconnaissance, vulnerability scanning, SQL injection, XSS, and security recommendations.

## Overview

This project involved performing a structured security assessment of a web application to identify, validate, and document security vulnerabilities.

The assessment covered reconnaissance, network and server scanning, vulnerability identification, SQL injection testing, Cross-Site Scripting (XSS), proof-of-concept exploitation, and security recommendations.

## Target

**Target:** testphp.vulnweb.com

**Assessment Date:** 28 March 2025

**Assessment Type:** Ethical Web Application Penetration Testing

> This project was conducted against a deliberately vulnerable application intended for security testing and educational purposes.

## Objectives

- Identify security vulnerabilities in the target web application.
- Perform reconnaissance and technology fingerprinting.
- Identify exposed services and potential security weaknesses.
- Test for SQL injection vulnerabilities.
- Test for Cross-Site Scripting (XSS).
- Validate identified vulnerabilities through controlled proof-of-concept testing.
- Document findings and recommend appropriate mitigation measures.

## Methodology

The assessment followed the following stages:

1. Reconnaissance
2. Vulnerability Scanning
3. Exploitation and Proof of Concept
4. Analysis of Findings
5. Recommendations and Reporting

## Tools Used

| Tool | Purpose |
|---|---|
| Nmap | Network and port scanning |
| WhatWeb | Web technology fingerprinting |
| Wappalyzer | Technology identification |
| Nikto | Web server vulnerability scanning |
| SQLMap | SQL injection testing |
| Burp Suite | Web application testing |
| Manual Payloads | Proof-of-concept validation |

## Reconnaissance

Initial reconnaissance was performed using Nmap, WhatWeb, and Wappalyzer.

The assessment identified technologies including:

- Nginx 1.19.0
- PHP 5.6.40
- MySQL
- Linux Ubuntu

Network scanning identified HTTP service availability on port 80.

## Vulnerability Assessment

### 1. SQL Injection

SQL injection was identified in the `cat` GET parameter.

Testing identified multiple SQL injection techniques:

- Boolean-based Blind SQL Injection
- Error-based SQL Injection
- Time-based Blind SQL Injection
- UNION-based SQL Injection

The UNION-based testing identified an 11-column structure, and the backend database was confirmed as MySQL.

Further testing demonstrated the ability to extract database information, including database names, tables, and user-related information.

### 2. Cross-Site Scripting (XSS)

A Cross-Site Scripting vulnerability was identified in the guestbook comment functionality.

A proof-of-concept JavaScript payload successfully executed in the application, demonstrating that user-controlled input could be interpreted as executable script.

Potential impacts include:

- Session hijacking
- Data theft
- Malicious script execution in a victim's browser

## Key Findings

| Finding | Description |
|---|---|
| SQL Injection | The `cat` parameter was vulnerable to multiple forms of SQL injection. |
| Cross-Site Scripting | User-supplied input in the guestbook functionality could execute JavaScript. |
| Outdated Software | The assessment identified outdated versions of Nginx and PHP. |
| Missing Security Headers | Security headers including X-Frame-Options and X-XSS-Protection were absent. |
| Exposed HTTP Headers | HTTP response headers disclosed additional information about the server. |

## Recommendations

### SQL Injection

- Use parameterized queries and prepared statements.
- Apply the principle of least privilege to database accounts.
- Deploy appropriate web application firewall protections.

### Cross-Site Scripting

- Validate and sanitize user input.
- Apply appropriate output encoding.
- Implement Content Security Policy (CSP).

### Server Hardening

- Upgrade outdated PHP and web server components.
- Apply current security patches.
- Configure appropriate HTTP security headers.
- Implement HTTPS/TLS.
- Conduct periodic penetration testing and security audits.

## Skills Demonstrated

- Web Application Security
- Ethical Hacking
- Penetration Testing
- Reconnaissance
- Vulnerability Assessment
- SQL Injection Testing
- Cross-Site Scripting Testing
- Network Scanning
- Security Reporting
- Vulnerability Mitigation

## Disclaimer

This project was conducted for educational and ethical security testing purposes against a deliberately vulnerable application.

No unauthorized systems were targeted.
