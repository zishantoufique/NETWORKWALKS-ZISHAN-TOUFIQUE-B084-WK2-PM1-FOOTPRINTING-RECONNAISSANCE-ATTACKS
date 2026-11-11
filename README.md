
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
