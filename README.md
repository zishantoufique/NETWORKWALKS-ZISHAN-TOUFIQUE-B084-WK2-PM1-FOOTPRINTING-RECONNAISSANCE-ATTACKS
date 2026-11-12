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

<img width="1535" height="817" alt="whois" src="https://github.com/user-attachments/assets/920a1594-07c4-459e-a568-a852b6c1d285" />

Findings:
- Domain is registered and publicly available
- Registrar, creation date, expiry date and name servers were identified
- Registrant information is privacy-protected
- Hosting provider identified as HostGator

---

### 🔹 Step 2. WhatWeb - Technology Fingerprinting

Commands: whatweb networkwalks.com / whatweb -v networkwalks.com

<img width="1535" height="814" alt="whatweb" src="https://github.com/user-attachments/assets/37218ce0-b45d-44b4-ab87-252d6c574396" />


Findings:
- Website is built on WordPress 7.0.4
- Plugin identified: WP Download Manager 3.3.58
- Server and other web technologies were fingerprinted
- This information helps to identify outdated / vulnerable versions

---

### 🔹 Step 3. Nslookup - DNS Resolution

Command: nslookup networkwalks.com

<img width="1531" height="815" alt="nslookup" src="https://github.com/user-attachments/assets/28535777-5272-4f15-8e96-717f41b913dd" />


Findings:
- Domain resolves to IP address: [REDACTED]
- DNS server responded successfully
- Confirmed the target is live and reachable

---

### 🔹 Step 4. Curl - HTTP Header Inspection

Command: curl -I https://networkwalks.com

<img width="1534" height="812" alt="curl" src="https://github.com/user-attachments/assets/94999181-c614-48a2-8c78-b48684cc6a8e" />


Findings:
- HTTP response code: 200 OK
- Server header information collected
- Content-Type, Date and other security headers observed
- Server is running and responding to HTTPS requests

---

### 🔹 Step 5. Wafw00f - WAF Detection

Commands: wafw00f networkwalks.com / wafw00f https://networkwalks.com

<img width="1535" height="819" alt="wafw00f" src="https://github.com/user-attachments/assets/d8587743-657b-4ac8-97f1-b04390a8812f" />


Findings:
- WAF Detected: ModSecurity (SpiderLabs)
- The site is protected by a Web Application Firewall
- This means direct attacks will be filtered / blocked

---

### 🔹 Step 6. Dnsrecon - DNS Enumeration

Command: dnsrecon -d networkwalks.com

<img width="1535" height="817" alt="dnsrecon" src="https://github.com/user-attachments/assets/41d17a32-97dc-45b3-ab68-acac4f817e13" />


Findings:
- DNS enumeration performed successfully
- Name servers, mail servers (MX) and other DNS records identified
- DNS Server: Bind 9.16.23
- SPF record found
- cPanel related records found

---


### 🔹 Step 7. Nmap - Port Scanning & Service Detection

Commands: nmap -sV networkwalks.com / nmap -T4 -A -v networkwalks.com

<img width="1535" height="819" alt="nmap -sv" src="https://github.com/user-attachments/assets/c04c2104-af0c-4a4c-8e03-e92129eed93c" />


Findings:
- Target is live and responding to scan
- Open ports identified: Port 80 (HTTP) and Port 443 (HTTPS)
- Services running on open ports were detected
- Service version detection performed using -sV option
- Other ports are filtered / closed due to firewall protection
- This helps to understand which services are exposed to the internet

Summary: By combining the results from all seven tools, I was able to collect information from several different layers of the target's public-facing infrastructure.

---

### 🔹 Step 8. Zenmap - Graphical Network Scanning

For Zenmap scanning, I used scanme.nmap.org which is the official test target provided by Nmap for legal scanning practice. This allowed me to perform an Intense Scan without scanning an unauthorized target.

Profile Used: Intense Scan
Command: nmap -T4 -A -v scanme.nmap.org

<img width="1532" height="814" alt="zenmap intense scan" src="https://github.com/user-attachments/assets/f0913689-5888-4103-be73-4bac16cd39f8" />

Findings:
- Target: scanme.nmap.org (45.33.32.156) is live and responding
- Host is up, latency observed
- OS Detection performed with Nmap -A option
- Service and version detection completed
- Traceroute information collected


#### 8.1 Topology View

<img width="1535" height="812" alt="zenmap_topology_blurred" src="https://github.com/user-attachments/assets/02fd4cd0-2548-4c9b-b02f-044cd8f9b471" />



Findings:
- Topology view shows the network path from localhost (attacker machine) to the target host
- Target host is shown as a node at the end of the route
- Topology helps to understand how many hops are between attacker and target

#### 8.2 Ping Scan

A Ping Scan was performed using Zenmap to discover live hosts on the network. The scan helped identify active devices and their IP addresses without scanning ports.

<img width="1535" height="817" alt="zenmap_nmap_blurred" src="https://github.com/user-attachments/assets/4a4ef1ec-7a9b-416d-8722-8c4d3e6aa7ae" />

#### 8.3 MAC of Local IP

<img width="1535" height="819" alt="ipconfig_blurred" src="https://github.com/user-attachments/assets/d54c71cd-2031-467c-a539-e4442aec2046" />


### 🔹 Step 9. theHarvester

Used to discover publicly available email addresses and subdomains.

<img width="1530" height="818" alt="theharvestor" src="https://github.com/user-attachments/assets/aa4383ff-be81-4132-ad88-156325102fff" />


<img width="1534" height="817" alt="theharvestor 2" src="https://github.com/user-attachments/assets/48822cd2-76c0-4fa7-baf5-009c61ab8d15" />


### 🔹 Step 10. Maltego

Used to visualize domain-related entities and their relationships. The graph identified an associated email address.

<img width="1535" height="814" alt="maltego" src="https://github.com/user-attachments/assets/80d6d0cc-eaa8-4e3e-b576-a34c1c9479fb" />




## ⚠️ 5. ERRORS FACED & SOLUTIONS

During this task I faced errors. The error screenshots are saved in the errors folder in this repo.

<img width="1533" height="815" alt="whatweb error" src="https://github.com/user-attachments/assets/d18b4e51-321a-4b8a-871f-498abdc76fc7" />



| Error | Cause | Solution |
| --- | --- | --- |
| dnsrecon - command not found | dnsrecon was not installed by default in Kali VM | Installed using - sudo apt update && sudo apt install dnsrecon -y |
| whois - Timeout / No response | Slow internet in VM / Server response delay | Ran the command again after few seconds, got full output |
| curl - SSL / Connection delay | HTTPS handshake took time / Network delay | Used curl -I with https, waited, checked internet connection |
| wafw00f - Slow scan | WAF detection sends multiple requests, takes time | Waited for scan to complete without closing terminal |
| nmap - Slow scan / Filtered ports | Firewall blocking / filtering some ports | Used nmap -sV, waited for scan to complete, checked open ports 80 and 443 only |
| Zenmap - Scan took time | Intense Scan (-A) does OS + version + traceroute, takes longer | Waited for scan to finish, did not close Zenmap, checked Nmap Output tab |

Lesson Learned: Always check if the tool is installed before running, check internet connection in VM, and wait for the scan to complete.

---

## 📊 6. RISK ANALYSIS / IMPACT

| # | Risk / Finding | Evidence / Observation | Potential Impact | Risk Level |
| --- | --- | --- | --- | --- |
| 1 | Domain registration and infrastructure information exposed | WHOIS revealed registrar and HostGator name servers. Registration and expiry dates are publicly available | Information can support reconnaissance and help attackers understand the domain's infrastructure | Low |
| 2 | Web technology information exposed | WhatWeb identified WordPress 7.0.4 and WP Download Manager 3.3.58 | Attackers may use exposed technology / version information to identify software requiring further security review | Medium |
| 3 | Server IP address identifiable | Nslookup resolved the domain to [REDACTED] | Provides information about the network location of the web service | Low |
| 4 | HTTP technical information exposed | Curl returned HTTP response headers | May assist technology fingerprinting and further enumeration | Low |
| 5 | WAF technology identifiable | Wafw00f identified ModSecurity (SpiderLabs) | Reveals information about the web application's security architecture | Low |
| 6 | DNS infrastructure information exposed | Dnsrecon identified DNS, mail, and service-related records, Bind 9.16.23 | DNS information can help build a broader infrastructure profile | Medium |
| 7 | Open ports and services exposed (networkwalks.com) | Nmap identified open ports 80 and 443 | Every open service widens the attack surface | Medium |
| 8 | Multiple open ports and services exposed (scanme.nmap.org - Zenmap) | Zenmap Intense Scan on scanme.nmap.org identified multiple open ports with service versions, including 22, 80, 3306 and 2222 | Each open service is a potential entry point if not patched and hardened. Exposed database port 3306 increases risk | High |
| 9 | OS information exposed (Zenmap) | Zenmap Hosts Viewer identified OS as Linux with high accuracy | OS fingerprinting helps attackers select OS-specific techniques | Low |

Risk Level Key: Critical / High / Medium / Low

The risks listed above are based on observations made during the footprinting and network scanning exercises and should not be considered confirmed vulnerabilities. No exploitation or vulnerability verification was carried out during this module.

---

## 💡 7. RECOMMENDATIONS

| # | Finding | Recommendation |
| --- | --- | --- |
| 1 | Domain registration information exposed | Enable domain privacy where appropriate and minimize publicly available administrative information |
| 2 | Web technology information exposed | Keep WordPress and all installed plugins updated, remove unused components, and regularly assess exposed software for known vulnerabilities |
| 3 | Server IP address identifiable | Protect the origin server with appropriate network controls and, where applicable, a reverse proxy or CDN |
| 4 | HTTP technical information exposed | Review response headers to minimize unnecessary technical disclosure |
| 5 | WAF technology identifiable | Keep ModSecurity and its rulesets properly maintained, regularly review WAF configurations and logs |
| 6 | DNS infrastructure information exposed | Review DNS records regularly and remove unnecessary or obsolete entries |
| 7 | Open ports visible (networkwalks.com + Zenmap) | Close unused ports, disable unnecessary services, only expose required ports, and maintain up-to-date asset inventory. Block public access to database port 3306 |
| 8 | OS information exposed (Zenmap) | Keep OS patched and updated, limit OS fingerprinting where possible by firewall rules |

---

## ✅ 8. CONCLUSION

During Week 2 of my Cybersecurity & Ethical Hacking internship, I worked on footprinting, OSINT, and network scanning. These activities allowed me to practice gathering publicly available information about organizations and identifying active hosts and services.

For the footprinting activities, I used WHOIS, WhatWeb, Nslookup, Curl, Wafw00f, DNSRecon and Nmap on networkwalks.com. For graphical scanning, I used Zenmap with Intense Scan profile on scanme.nmap.org, the official Nmap test target. Each tool provided a different type of information, helping me understand how multiple sources and techniques can be combined to build a broader picture of a target's public-facing environment.

One of the main lessons from this week was the importance of reconnaissance and information gathering before further security testing. I also learned that not every piece of publicly available information represents a vulnerability and that findings must be interpreted in context.

Finally, these activities reinforced the importance of accurate documentation, risk assessment, and authorized testing. All exercises documented in this report were conducted within the assigned educational and internship scope.

### 🎓 What I Learned

- 1. Passive vs Active Reconnaissance - WHOIS, Nslookup, and Dnsrecon are passive / semi-passive, while WhatWeb and Curl involve direct HTTP requests
- 2. Technology Fingerprinting - Identifying CMS, plugin versions, and frameworks helps build a picture of a target's attack surface
- 3. WAF Detection - Detecting a WAF early helps a tester understand what defenses are in place
- 4. DNS Enumeration - SOA, NS, MX, TXT, and SRV records reveal infrastructure details like mail hosting
- 5. Port Scanning - Nmap shows which services are exposed to the internet
- 6. Zenmap Visualization - Zenmap Topology and Hosts Viewer make Nmap results easier to understand visually, including OS detection and network path
- 7. Documentation - Documenting each tool, command, and finding clearly is a core part of professional reconnaissance reporting

---

## 🔗 10. SOURCES & REFERENCES

- Target Website: https://networkwalks.com
- Kali Linux Official Tools: https://www.kali.org/tools/
- WHOIS Tool: https://www.kali.org/tools/whois/
- WhatWeb Tool: https://www.kali.org/tools/whatweb/
- Dnsrecon Tool: https://www.kali.org/tools/dnsrecon/
- WAFW00F Tool: https://www.kali.org/tools/wafw00f/
- Nmap Tool: https://nmap.org/
- Nmap Kali Tool: https://www.kali.org/tools/nmap/
- Zenmap Tool: https://nmap.org/zenmap/
- Scanme Test Target: https://scanme.nmap.org/
- Curl Documentation: https://curl.se/docs/
- Networkwalks Cybersecurity Program: https://networkwalks.com

---

## 👩‍💻 Author

Zishan Toufique
- Cybersecurity Professional - B084, Networkwalks
- Program: Cybersecurity Internship - Networkwalks
- Week: 02
- Topic: Footprinting, Network Scanning and Vulnerability Assessment / Analysis
- Repository: GitHub

-End-
