🔍 PENETRATION TESTING REPORT
🕵️ FOOTPRINTING, NETWORK SCANNING AND VULNERABILITY ASSESSMENT / ANALYSIS
Field	Information
👩‍💻 Cybersecurity Professional	Naduni Umeda
🎓 Program / Batch	B084 - Networkwalks
📅 Date	08 November 2026
📚 Modules Completed	W2-PM1 Footprinting with multiple Kali tools + Zenmap Scanning
🎯 Client / Target	Networkwalks (secured with permission already) / scanme.nmap.org (for Zenmap)
✅ Permission secured from client?	Yes
🔄 Phases covered	Phase 1. Reconnaissance and Footprinting / Phase 2. Scanning and Network Discovery / Phase 3. Vulnerability Assessment / Analysis
⚖️ 1. LIABILITY DISCLAIMER
I have performed these activities only on the systems & devices where I had secured written permission or the devices / systems that I own myself.
All these materials are for education and research purpose only.
Do not use anything from here to break the law.
The instructor, the authors and Networkwalks are not responsible for what you do with this knowledge.
Every action you take is your own responsibility.
Misuse can lead to criminal charges, heavy fines, loss of your job and a permanent record.
In most countries unauthorised access is a crime even when nothing is damaged.
📖 2. INTRODUCTION
This report documents my Week 2 work as part of my ongoing internship program at Networkwalks. It covers footprinting the networkwalks.com domain using multiple Kali Linux tools (W2-PM1) and network scanning using Zenmap on scanme.nmap.org, the official Nmap test target.

The activities focus on different reconnaissance and information-gathering techniques, from:

Collecting publicly available information about a target
Identifying live hosts and services within a network
Understanding the target's public-facing infrastructure
Visualizing network topology and OS detection using Zenmap
For each activity, I documented:

Commands performed
Results observed
Screenshots as evidence
Short explanation of why the information could be relevant from a security perspective
🛠️ 3. TOOLS USED
Tool	Purpose
Kali Linux	Operating system used for reconnaissance activities
whois	Find who owns the domain, when it was registered, and its name servers
whatweb	Fingerprint web technologies (server, CMS, plugins, IP)
nslookup	Resolve the domain name to its IP address using DNS
curl -I	Read the HTTP response headers of the website
wafw00f	Detect whether a Web Application Firewall protects the site
dnsrecon	Enumerate all DNS records (NS, MX, SPF, TXT, SRV)
nmap / Zenmap	Scan to find live hosts, open ports, services and versions
Zenmap	Graphical interface for Nmap - for topology, ports/hosts view and OS detection
