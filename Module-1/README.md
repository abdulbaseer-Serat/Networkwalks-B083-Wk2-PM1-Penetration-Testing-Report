<div align="center">

#  Penetration Testing Report Module-1
### Footprinting & Reconnaissance with Multiple Kali Tools

![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![Module](https://img.shields.io/badge/Module-W2--PM1-blue?style=for-the-badge)
![Program](https://img.shields.io/badge/Program-Networkwalks%20Internship-red?style=for-the-badge)
![Purpose](https://img.shields.io/badge/Purpose-Educational%20Only-orange?style=for-the-badge)

*A hands-on reconnaissance exercise mapping the public footprint of a live domain using six Kali Linux tools.*

</div>

---

## 📋 Report Details

| Field | Detail |
|---|---|
|  **Pentester Name** | `Abdulbaseer Serat` |
|  **Program / Batch** | Networkwalks Internship |
|  **Date** | 14 Sep 2026 |
|  **Module Completed** | W2-PM1 — Footprinting with Multiple Kali Tools |
|  **Target** | `networkwalks.com` *(secured written permission)* |
|  **Permission Secured** | Yes |
|  **Phase Covered** | Phase 1 — Reconnaissance & Footprinting |

---

##  ⚠️ Legal & Ethical Disclaimer

> This repository is provided for **educational, research, and authorized security testing purposes only**.
> All content was developed and tested in authorized environments with proper permission. Unauthorized access to systems, networks, or applications is illegal and unethical.
> Users are solely responsible for complying with applicable laws and obtaining proper authorization before performing any security-related activities.

---

## 🧭 Introduction

This report documents the **Footprinting and Reconnaissance** phase conducted against `networkwalks.com` as part of the **W2-PM1** module.

Footprinting is the initial stage of a penetration test and serves as the foundation for understanding a target's external attack surface. During this phase, publicly available information is collected to identify key details about the target, including domain ownership, hosting infrastructure, IP addresses, DNS records, security controls, and underlying technologies.

The objective is to build an accurate profile of the target using open-source intelligence (OSINT) and passive reconnaissance techniques before any direct interaction with the environment occurs.

All commands below were executed inside **Kali Linux**, with the exact command, observed result, a screenshot as evidence, and a short analysis of why each finding matters from an attacker's perspective.

---

## 🛠️ Tools Used

| 🔧 Tool | 🎯 Purpose |
|---|---|
| **Kali Linux** | Operating system used for all reconnaissance activities |
| **WHOIS** | Domain registration details (owner, dates, name servers) |
| **WhatWeb** | Fingerprints web technologies (server, CMS, plugins, IP) |
| **Nslookup** | Resolves the domain name to its IP address via DNS |
| **curl -I** | Reads the HTTP response headers of the website |
| **Wafw00f** | Detects whether a Web Application Firewall is present |
| **DNSRecon** | Enumerates DNS records (NS, MX, SPF, TXT, SRV) |

---

## Activities Performed

###  Task 1 — WHOIS Lookup
**Goal:** Used to retrieve domain registration information, including registrar details, registration dates, and name servers.

```bash
whois networkwalks.com
```

<div align="center">
<img width="975" height="619" alt="Whois" src="https://github.com/user-attachments/assets/d60e3f01-9696-4424-8f11-e52d5eaefec4" />

📸 *Screenshot: WHOIS output*

</div>

** How attackers use this:** WHOIS reveals the registrar, registration/expiry dates, and name servers — instantly exposing the hosting provider. Abuse contacts and registration dates can also aid social engineering.

---

###  Task 2 — WhatWeb Fingerprinting
**Goal:** Identify the web server, CMS, plugins, frameworks, and IP address.

```bash
whatweb networkwalks.com
```

<div align="center">

📸 *Screenshot: WhatWeb output*

<img width="643" height="514" alt="whatweb command" src="https://github.com/user-attachments/assets/7e662b87-a4aa-4a1e-b9f4-6080ea7e5e49" />


</div>

** How attackers use this:** WhatWeb exposes exact software versions (e.g. CMS + plugin versions). Attackers cross-reference these against public vulnerability databases to find known exploits.

---

###  Task 3 — Nslookup DNS Resolution
**Goal:** Resolve the domain name to its IP address.

```bash
nslookup networkwalks.com
```

<div align="center">

📸 *Screenshot: Nslookup output*

<img width="643" height="512" alt="nslookup command" src="https://github.com/user-attachments/assets/76d17307-b08c-4891-bb34-8f4135233a06" />


</div>

** How attackers use this:** Knowing the real IP lets an attacker scan the server directly, discover co-hosted sites, and start mapping the target's infrastructure.

---

###  Task 4 — HTTP Header Inspection
**Goal:** Read the HTTP response headers — server banner, status, cookies, and redirects.

```bash
curl -I https://networkwalks.com
```

<div align="center">

📸 *Screenshot: curl output*

<img width="652" height="511" alt="curl-I command" src="https://github.com/user-attachments/assets/44daa7ee-f8bd-46a0-9300-538f2c68ab5d" />


</div>

** How attackers use this:** Headers leak the web server, caching layer, and hidden API endpoints — giving fingerprinting clues without even loading the full page.

---

###  Task 5 — WAF Detection
**Goal:** Detect whether a Web Application Firewall is protecting the target.

```bash
wafw00f networkwalks.com
```

<div align="center">

📸 *Screenshot: Wafw00f output*

<img width="644" height="430" alt="waf command" src="https://github.com/user-attachments/assets/bf6b3faf-32b7-4105-9d79-9b8ccfb0aa61" />

</div>

** How attackers use this:** Knowing a WAF is present shapes the whole attack strategy — naive attempts get blocked or logged, so an attacker must adapt or attempt a bypass.

---

###  Task 6 — DNS Enumeration
**Goal:** Enumerate all DNS records — name servers, mail servers, SPF, TXT, and SRV records.

```bash
dnsrecon -d networkwalks.com
```

<div align="center">

📸 *Screenshot: DNSRecon output*

<img width="650" height="513" alt="dns recon command" src="https://github.com/user-attachments/assets/43c50888-cbfb-4677-aca2-a1bd7ef37350" />


</div>

** How attackers use this:** DNSRecon maps the entire DNS footprint — mail servers, DNS software version, SPF policy, and service records — building a broader infrastructure profile.

---

##  Risk Analysis / Impact

| # |  Risk / Finding | Evidence |  Potential Impact |  Risk Level |
|---|---|---|---|---|
| 1 | Web technology exposed | WhatWeb identified CMS + plugin versions | Attackers may target known vulnerabilities for that version | 🟠 Medium |
| 2 | Server IP identifiable | Nslookup resolved public IP address | Reveals network location of the web service | 🟢 Low |
| 3 | HTTP info exposed | curl returned headers + hidden endpoints | Assists fingerprinting and further enumeration | 🟢 Low |
| 4 | WAF technology identifiable | Wafw00f detected the WAF vendor | Reveals security architecture details | 🟢 Low |
| 5 | DNS infrastructure exposed | DNSRecon enumerated DNS/mail/SRV records | Helps build a broader infrastructure profile | 🟠 Medium |

> **Risk Key:** 🔴 Critical &nbsp;|&nbsp; 🟠 Medium &nbsp;|&nbsp; 🟢 Low

> **Note:** These are *observations*, not confirmed vulnerabilities. Only information gathering was performed — no exploitation. The presence of a version number, IP, or DNS record does not by itself prove a system is vulnerable; further authorized testing would be required to confirm any real risk.

---

## ✅ Recommendations

-  **Review exposed technology info** — audit what CMS/plugin/server details are publicly visible.
-  **Keep software updated** — patch CMS platforms and plugins against current advisories.
-  **Review HTTP headers** — strip unnecessary technical details from responses.
-  **Audit DNS records regularly** — ensure only required records are publicly exposed.
-  **Maintain and tune the WAF** — keep it enabled and monitored.
-  **Run internal recon periodically** — see your own footprint the way an attacker would.
-  **Test only with authorization** — reconnaissance and scanning must always stay in scope.

---

## 🏁 Conclusion

This module walked through the **first stage of any real attack: reconnaissance**. Using six Kali Linux tools — WHOIS, WhatWeb, Nslookup, curl, Wafw00f, and DNSRecon — a full public profile of `networkwalks.com` was built without ever touching the target directly.

The key takeaway: **information gathering is powerful precisely because it's silent.** Every technical finding was documented with what was performed, what was discovered, why it matters, and how the risk can be reduced — the foundation of a professional security report. All testing was carried out strictly within the authorized scope of this educational lab.

---

##  Evidence Collected

All screenshots are stored in the [`screenshots/`](./screenshots) folder:

- [ ] `whois.png`
- [ ] `whatweb.png`
- [ ] `nslookup.png`
- [ ] `curl.png`
- [ ] `wafw00f.png`
- [ ] `dnsrecon.png`

---

<div align="center">

**— End of Report —**

*Made during the Networkwalks Cybersecurity & Ethical Hacking Internship 🇵🇰*

</div>
