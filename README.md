
# 🔍 PENETRATION TESTING REPORT

## 🕵️ FOOTPRINTING, NETWORK SCANNING AND VULNERABILITY ASSESSMENT / ANALYSIS

| **Field** | **Information** |
|---|---|
| 👨‍💻 Cybersecurity Professional | Zishan Toufique |
| 🎓 Program / Batch | B084 - Networkwalks |
| 📅 Date | 08 November 2026 |
| 📚 Modules Completed | W2-PM1 Footprinting with Multiple Kali Linux Tools + Zenmap Scanning |
| 🎯 Client / Target | Networkwalks (`networkwalks.com`) / Authorized VirtualBox Lab Network |
| ✅ Permission secured from client? | Yes, for the authorized assessment scope |
| 🔄 Phases covered | Phase 1. Reconnaissance and Footprinting / Phase 2. Scanning and Network Discovery / Phase 3. Vulnerability Assessment and Analysis |

---

## ⚖️ 1. LIABILITY DISCLAIMER

- I have performed these activities only on systems and devices where I had secured permission or systems that I own.
- All these materials are intended for educational and research purposes only.
- Do not use anything from this repository to break the law.
- The instructor, authors and Networkwalks are not responsible for any misuse of the knowledge shared here.
- Every action you take is your own responsibility.
- Misuse can lead to criminal charges, heavy fines, loss of employment and a permanent criminal record.
- In most countries, unauthorized access to computer systems is a crime, even when no damage is caused.

---

## 📖 2. INTRODUCTION

This report documents my Week 2 practical work as part of my ongoing cybersecurity internship program at Networkwalks.

It covers footprinting and reconnaissance of the `networkwalks.com` domain using multiple Kali Linux tools (W2-PM1), along with network scanning and discovery using Zenmap.

The activities focus on different reconnaissance and information-gathering techniques, including:

- Collecting publicly available information about a target domain.
- Identifying domain ownership and registration information.
- Discovering DNS records and resolving domain names into IP addresses.
- Identifying web technologies and server information.
- Checking for Web Application Firewall (WAF) protection.
- Identifying live hosts and available network services within an authorized lab network.
- Understanding network topology and interpreting scan results.
- Analysing the collected information from a cybersecurity perspective.

For each activity, I documented:

- Commands performed.
- Results observed.
- Screenshots as practical evidence.
- Short explanations of the purpose of each tool.
- Security observations and potential risks.
- Recommendations for improving security.

---

## 🛠️ 3. TOOLS USED

| **Tool** | **Purpose** |
|---|---|
| Kali Linux | Operating system used for reconnaissance and security assessment activities. |
| WHOIS | Retrieves domain registration details, registrar information and name servers. |
| WhatWeb | Identifies web technologies, server details and website components. |
| Nslookup | Resolves domain names into IP addresses using DNS. |
| curl -I | Retrieves HTTP response headers from a website. |
| WAFW00F | Identifies whether a website is protected by a Web Application Firewall. |
| DNSRecon | Enumerates DNS records such as NS, MX, TXT, SPF and other records. |
| Nmap | Discovers hosts, open ports, services and service versions. |
| Zenmap | Graphical interface for Nmap used to visualize scan results, network topology and host information. |

---

### 💻 Lab Configuration

| Component | Configuration |
| --- | --- |
| Host OS | Windows 11 |
| Attacker Machine | Kali Linux (VM) |
| Target 1 | networkwalks.com |
| Target 1 IP | [REDACTED - Hidden for Privacy] |
| Target 2 (Zenmap) | scanme.nmap.org |
| Target 2 IP | 45.33.32.156 |
| Tools Used | whois, whatweb, nslookup, curl, wafw00f, dnsrecon, nmap, Zenmap |

---

## 🎯 4. ACTIVITIES PERFORMED

### 4.1. Footprinting with multiple Kali tools

As part of the reconnaissance phase, I analyzed the networkwalks.com domain using seven different tools available in Kali Linux: WHOIS, WhatWeb, Nslookup, Curl, Wafw00f, DNSRecon and Nmap.

Each tool provided a different perspective of the target, allowing me to gradually build a broader picture of its domain, DNS, and web infrastructure.

---

### 🔹 Step 1. WHOIS Lookup

Command: whois networkwalks.com

![WHOIS Lookup](<img width="1535" height="817" alt="whois" src="https://github.com/user-attachments/assets/c26e6cc3-5b89-4ed1-bac1-2c082ffcaaff" />)

Findings:
- Domain is registered and publicly available
- Registrar, creation date, expiry date and name servers were identified
- Registrant information is privacy-protected
- Hosting provider identified as HostGator

---

### 🔹 Step 2. WhatWeb - Technology Fingerprinting

Commands: whatweb networkwalks.com / whatweb -v networkwalks.com

![WhatWeb Scan](screenshots/02-whatweb.png)

Findings:
- Website is built on WordPress 7.0.4
- Plugin identified: WP Download Manager 3.3.58
- Server and other web technologies were fingerprinted
- This information helps to identify outdated / vulnerable versions

---

### 🔹 Step 3. Nslookup - DNS Resolution

Command: nslookup networkwalks.com

![Nslookup Result](screenshots/03-nslookup.png)

Findings:
- Domain resolves to IP address: [REDACTED]
- DNS server responded successfully
- Confirmed the target is live and reachable

---

### 🔹 Step 4. Curl - HTTP Header Inspection

Command: curl -I https://networkwalks.com

![Curl Headers](screenshots/04-curl.png)

Findings:
- HTTP response code: 200 OK
- Server header information collected
- Content-Type, Date and other security headers observed
- Server is running and responding to HTTPS requests

---

### 🔹 Step 5. Wafw00f - WAF Detection

Commands: wafw00f networkwalks.com / wafw00f https://networkwalks.com

![Wafw00f Result](screenshots/05-wafw00f.png)

Findings:
- WAF Detected: ModSecurity (SpiderLabs)
- The site is protected by a Web Application Firewall
- This means direct attacks will be filtered / blocked

---

### 🔹 Step 6. Dnsrecon - DNS Enumeration

Command: dnsrecon -d networkwalks.com

![Dnsrecon Result](screenshots/06-dnsrecon.png)

Findings:
- DNS enumeration performed successfully
- Name servers, mail servers (MX) and other DNS records identified
- DNS Server: Bind 9.16.23
- SPF record found
- cPanel related records found

---
