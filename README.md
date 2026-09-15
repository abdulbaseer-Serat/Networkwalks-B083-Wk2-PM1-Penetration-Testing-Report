
<div align="center">

# 🛡️ Penetration Testing Final Report
### Footprinting, Information Gathering & Network Scanning

**Week 2 · Project Modules 1–5**
*Cybersecurity & Ethical Hacking Internship — NetworkWalks*

![Static Badge](https://img.shields.io/badge/STATUAS-COMPLETED-brightorange)
![Static Badge](https://img.shields.io/badge/ENVIRONMENT-KALI%20LINUX-orange)
![Static Badge](https://img.shields.io/badge/TESTING%20TYPE-AUTHORIZED%20%26%20EDUCATIONAL-red)

</div>

---

## 📌 Project Information

| Field | Details |
|---|---|
| **Project Title** | Penetration Testing – Footprinting, Information Gathering & Network Scanning |
| **Program** | Cybersecurity & Ethical Hacking Internship |
| **Organization** | NetworkWalks |
| **Week** | Week 2 |
| **Modules Completed** | W2-PM1 · W2-PM2 · W2-PM3 · W2-PM4 · W2-PM5 |
| **Operating Environment** | Kali Linux / VirtualBox |
| **Testing Type** | Educational & Authorized Security Assessment |
| **Phases Covered** | Reconnaissance, Footprinting, OSINT, Information Gathering, Network Discovery |

---

## ⚠️ Liability Disclaimer

> This project was performed **strictly for educational, research, and authorized cybersecurity training purposes.**

All reconnaissance, information gathering, and network scanning activities were performed only against:

- ✅ Publicly available information where appropriate
- ✅ Targets included within the authorized educational scope
- ✅ Systems specifically permitted for testing
- ✅ My own local network and virtualized lab environment

🚫 **No** unauthorized access, exploitation, privilege escalation, denial-of-service activity, credential attacks, malware deployment, persistence techniques, or destructive actions were performed.

All findings in this report are **security observations**, not confirmed vulnerabilities, unless explicitly validated through further authorized testing.

---

## 🧭 Modules Completed

| # | Module | Focus Area |
|---|---|---|
| 🕵️ **W2-PM1** | Multiple Kali Linux Footprinting Tools | WHOIS, WhatWeb, Nslookup, Curl, Wafw00f, DNSRecon |
| 🔎 **W2-PM2** | Google Hacking Database (GHDB) | Search-engine-based reconnaissance |
| 🕸️ **W2-PM3** | OSINT via Maltego | Graphical entity & relationship mapping |
| 📧 **W2-PM4** | theHarvester | Email & host discovery |
| 🌐 **W2-PM5** | Zenmap | Network scanning & topology mapping |

---

## 🎯 Objectives

- Understand the reconnaissance phase of penetration testing
- Perform footprinting using multiple Kali Linux tools
- Collect publicly available information about an authorized target
- Explore search engine reconnaissance and the GHDB
- Use Maltego for graphical OSINT investigation
- Use theHarvester to discover public emails and hosts
- Identify the local network configuration & active devices
- Analyze scan results and generate a network topology using Zenmap
- Distinguish between *information exposure* and a *confirmed vulnerability*
- Document all activities with screenshots and evidence

---

## 🧰 Tools & Technologies

| Tool | Purpose |
|---|---|
| **Kali Linux** | Primary penetration testing environment |
| **VirtualBox** | Virtualization for the Kali Linux lab |
| **WHOIS** | Domain registration information |
| **WhatWeb** | Website technology fingerprinting |
| **Nslookup** | DNS resolution / domain-to-IP lookup |
| **Curl** | HTTP response header inspection |
| **Wafw00f** | Web Application Firewall detection |
| **DNSRecon** | DNS reconnaissance & record enumeration |
| **Google / GHDB** | Search-engine-based information discovery |
| **Maltego** | Graphical OSINT & entity relationship analysis |
| **theHarvester** | Public email, host & subdomain discovery |
| **ip addr** | Local network interface identification |
| **Zenmap** | Graphical Nmap scanning & topology visualization |
| **Nmap Ping Scan** | Active host discovery on authorized network |

---

## 🔬 Module Breakdown

### 🕵️ Module 1 — Footprinting with Kali Linux Tools

| Tool | What It Revealed | Risk |
|---|---|:---:|
| WHOIS | Domain registration, registrar, name servers, status | 🟢 Low |
| WhatWeb | Web server, CMS, frameworks, cookies, headers | 🟡 Medium |
| Nslookup | DNS resolution & infrastructure relationships | 🟡 Medium |
| Curl `-I` | HTTP headers, redirects, security headers | 🟢 Low |
| Wafw00f | Presence/type of Web Application Firewall | 🟢 Low |
| DNSRecon | Name servers, mail servers, TXT/SPF records | 🟡 Medium |

### 🔎 Module 2 — Google Hacking Database (GHDB)

Explored structured search operators to locate publicly indexed content, exposed documents, and cached information — reinforcing the need for organizations to audit what gets indexed by search engines.

### 🕸️ Module 3 — OSINT with Maltego

Used a domain entity as a starting point, ran transforms, and visually mapped relationships (e.g., domain → email entity) to build a graph-based view of the external footprint.

### 📧 Module 4 — theHarvester

Queried multiple sources against the authorized domain to collect public emails, hostnames, and subdomains — demonstrating how result completeness depends on source availability, API access, and rate limits.

### 🌐 Module 5 — Network Scanning with Zenmap

1. Identified local network config via `ip addr`
2. Ran a **Ping Scan** on the authorized subnet
3. Discovered active hosts: `10.0.0.1`, `10.0.0.2`
4. Generated and reviewed the **network topology**
5. Saved topology output as PDF evidence

---

## 📊 Summary of Findings

| # | Finding / Observation | Module | Risk |
|---|---|:---:|:---:|
| 1 | Public domain registration information available | PM1 | 🟢 Low |
| 2 | Web technologies can be fingerprinted | PM1 | 🟡 Medium |
| 3 | DNS information is publicly discoverable | PM1 | 🟡 Medium |
| 4 | HTTP headers expose technical behavior | PM1 | 🟢 Low |
| 5 | Security controls (e.g. WAF) can be identified | PM1 | 🟢 Low |
| 6 | Public search results may expose indexed resources | PM2 | 🟡 Medium |
| 7 | Entity relationships can be visually mapped | PM3 | 🟢 Low |
| 8 | Public email/host information discoverable | PM4 | 🟡 Medium |
| 9 | Multiple active hosts discovered on local network | PM5 | 🟡 Medium |
| 10 | Network topology successfully generated | PM5 | ⚪ Informational |

> No exploitation was performed. These findings are reconnaissance observations, not proof of a vulnerability.

---

## 🛡️ Risk Analysis Overview

| Area | Potential Impact | Risk |
|---|---|:---:|
| Public Information Exposure | Enables detailed target profiling | 🟡 Medium |
| Technology Fingerprinting | Flags systems needing security review | 🟡 Medium |
| Search Engine Indexing | May expose unintended public resources | 🟡 Medium |
| Public Email & Host Discovery | Aids social engineering / infra mapping | 🟡 Medium |
| Unknown Network Devices | Unverified devices in the environment | 🟡 Medium |

---

## ✅ Recommendations

- 🔁 Periodically review public information (domains, DNS, hosts, docs)
- 🛠️ Keep all public-facing software & frameworks updated
- 📋 Review HTTP headers for unnecessary technical exposure
- 🌐 Maintain DNS hygiene — remove unused/outdated records
- 🔍 Monitor and control search engine indexing of sensitive content
- 📧 Use role-based email addresses; monitor public exposure
- 🗂️ Maintain an accurate, up-to-date asset inventory
- 📡 Perform regular authorized network discovery
- ❓ Investigate every unknown host found during scans
- 🗺️ Keep network topology documentation current
- 🔐 Always operate within a clearly authorized scope

---

## 📚 Skills & Knowledge Gained

- **Reconnaissance & Footprinting** — domain info, fingerprinting, DNS, headers, WAF detection
- **Search Engine Reconnaissance** — GHDB operators & public exposure analysis
- **OSINT Analysis** — Maltego transforms & entity relationship mapping
- **Email & Host Discovery** — theHarvester across multiple sources
- **Network Scanning** — local discovery, ping scans, topology generation
- **Documentation** — evidence capture, risk analysis, professional reporting

---

## 🧩 Learning Outcome

Penetration testing does not begin with exploitation — it begins with understanding the target environment.

```
Traditional Footprinting
        ↓
Search Engine Reconnaissance
        ↓
Graphical OSINT Analysis (Maltego)
        ↓
Email & Host Discovery (theHarvester)
        ↓
Local Network Discovery & Topology Mapping (Zenmap)
```

A security professional must always understand **what** information is being collected, **where** it originates, **whether** the activity is authorized, and **what the results actually mean.**

---

## 🏁 Conclusion

During Week 2 of this internship, five practical modules covering footprinting, OSINT, information gathering, and network scanning were completed end-to-end — from domain-level reconnaissance to a fully mapped and saved local network topology.

Every activity reinforced a core principle of ethical hacking: **a significant amount can be learned about an environment before any exploitation begins**, and all of it must be gathered and reported responsibly, within authorized scope.

---

## 🗂️ Evidence Appendix

```
📁 Module 1 – Footprinting
   ├─ WHOIS command & output
   ├─ WhatWeb command & output
   ├─ Nslookup command & output
   ├─ Curl -I command & output
   ├─ Wafw00f command & output
   └─ DNSRecon command & output
```
<div align="center">
<img width="975" height="619" alt="Whois" src="https://github.com/user-attachments/assets/1d1a67cf-85e2-48c8-8c75-81ac9ca5d526" />
<img width="970" height="282" alt="nslookup" src="https://github.com/user-attachments/assets/af987e34-f08f-4f1f-9e69-56454eadffea" />
<img width="977" height="540" alt="dnsrecon" src="https://github.com/user-attachments/assets/cf5588d5-ab77-4e73-8168-60c5080f56af" />
</div>


```
📁 Module 2 – Google Hacking Database
   ├─ Task 1 search/dork + results
   └─ Task 2 search/dork + results
```



```
📁 Module 3 – Maltego
   ├─ Domain entity added
   ├─ Search/transform results
   ├─ Email discovery transform
   └─ Transform execution process
```


<div align="center">

<img width="956" height="867" alt="01-target-domain" src="https://github.com/user-attachments/assets/16bb23c7-68e9-4cdc-85fa-ddbc3b386d25" />
<img width="961" height="879" alt="02-email-transform" src="https://github.com/user-attachments/assets/9364f38e-de51-435c-b71b-38af91acf670" />
<img width="961" height="872" alt="03-email-search" src="https://github.com/user-attachments/assets/ee536fa7-97df-4a4e-96ba-22a1ac650870" />


</div>



```
📁 Module 4 – theHarvester
   ├─ theHarvester command
   ├─ Baidu source results
   └─ All available sources search/result
```

<div align="center">
<img width="1039" height="586" alt="Task 2 execution using all available OSINT data sources" src="https://github.com/user-attachments/assets/f747f61b-bf66-41bb-b540-71cf173d07d8" />
<img width="1247" height="903" alt="Task 1 execution using the Baidu search source against microsoft com" src="https://github.com/user-attachments/assets/bfeaab61-b319-410c-9d0f-546d281f219d" />


</div>


```
📁 Module 5 – Zenmap
   ├─ ip addr output
   ├─ Zenmap Ping Scan
   ├─ Hosts discovered
   ├─ Network topology
   ├─ Topology legend
   └─ Saved topology / PDF confirmation
```


<div align="center">

<img width="893" height="641" alt="ip addr" src="https://github.com/user-attachments/assets/2a664d98-0223-442a-92c4-344d0dc4de7e" />
<img width="722" height="687" alt="ping scan" src="https://github.com/user-attachments/assets/8dc68b2e-9b0c-4b41-b89b-cfda84f7fac5" />


</div>



<div align="center">

## 👤 Author

**Abdulbaseer Serat**
Cybersecurity & Ethical Hacking Internship · NetworkWalks
Week 02 — Footprinting, OSINT & Network Scanning
Modules: `W2-PM1` → `W2-PM5`

</div>
