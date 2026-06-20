# SQL Injection Attack Analysis using Wireshark

## Overview

This project analyzes a SQL Injection attack captured in a PCAP file using Wireshark.

The objective was to identify malicious HTTP requests, analyze attacker behavior, extract database information, and understand how credentials were compromised through SQL Injection.

---

## Tools Used

- Wireshark
- DVWA (Damn Vulnerable Web Application)
- MySQL
- CrackStation
- Cisco CyberOps Workstation

---

## Attack Summary

### Step 1: Identify Vulnerable Page

The attacker accessed the DVWA SQL Injection page.

### Step 2: SQL Injection Testing

The attacker inserted malicious SQL statements into the User ID field.

### Step 3: Database Enumeration

The attacker used UNION SELECT queries to retrieve:

- Database Name
- Current Database User

### Step 4: Table Enumeration

The attacker gathered information about database tables.

### Step 5: Password Hash Extraction

User password hashes were extracted from the database.

Example Hash:

8d3533d75ae2c3966d7e0d4fcc69216b

### Step 6: Hash Cracking

The extracted MD5 hash was analyzed using CrackStation.

Recovered Password:

charley

---

## Key Findings

- SQL Injection vulnerability existed.
- Database information was exposed.
- User credentials were compromised.
- Password hashes could be cracked easily.

---

## Skills Demonstrated

- Network Packet Analysis
- HTTP Traffic Inspection
- SQL Injection Detection
- Cyber Threat Investigation
- Wireshark Analysis
- Hash Analysis

---

## Mitigation Recommendations

- Use Prepared Statements
- Implement Input Validation
- Apply Parameterized Queries
- Deploy Web Application Firewalls
- Follow Secure Coding Practices

---

## Learning Outcomes

This lab demonstrated how attackers exploit SQL Injection vulnerabilities to access sensitive database information and why secure coding practices are critical for web application security.
