<div align="center">

#  Penetration Testing Report Module-1
### Footprinting & Reconnaissance with Multiple Kali Tools

![Static Badge](https://img.shields.io/badge/Status-Completed-red)
![Static Badge](https://img.shields.io/badge/Module-W2--PM1-brightgreen)
![Static Badge](https://img.shields.io/badge/Program-Networkwalks%20Intership-orange)
![Static Badge](https://img.shields.io/badge/Purpose-Only%20for%20Education%20-blue)

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
**Goal:** Query the public domain registration record to find who owns the domain, when it was registered, and its name servers.

```bash
whois networkwalks.com
```

<div align="center">
  
<img width="975" height="619" alt="Whois" src="https://github.com/user-attachments/assets/85c20216-b444-4900-961e-61833855cb6c" />

📸 *Screenshot: WHOIS output*

</div>

**How attackers use this:** WHOIS reveals the registrar, registration and expiry dates, and name servers. Here the name servers point to HostGator, so an attacker instantly learns the hosting provider. Registration dates and abuse contacts help with social engineering and planning.

---

###  Task 2 — Whatweb Fingerprinting
**Goal:** Used for web technology fingerprinting to identify the web server, CMS, frameworks, plugins, and hosting-related information.

```bash
whatweb networkwalks.com
```
<img width="973" height="447" alt="wafw00f" src="https://github.com/user-attachments/assets/d7ce85b4-d770-4c5c-be88-4d3e8bdc9b4f" />

<div align="center">

📸 *Screenshot: WhatWeb output*

</div>

**How attackers use this:** WhatWeb reveals the technologies and software versions in use, such as WordPress and installed plugins. Attackers can compare these versions against public vulnerability databases to identify known weaknesses. It may also disclose infrastructure details, including the server IP address and publicly exposed contact information, which can support further reconnaissance.

---

###  Task 3 — Nslookup DNS Resolution
**Goal:** Used to query DNS records and resolve the target domain to its associated IP address.

```bash
nslookup networkwalks.com
```

<div align="center">
  
 <img width="970" height="282" alt="nslookup" src="https://github.com/user-attachments/assets/52f4ad25-dabd-442b-870b-dd221a9f873e" />
 

📸 *Screenshot: Nslookup output*


</div>

**How attackers use this:** nslookup turns a domain name into its real IP address (192.232.216.135). Knowing the IP lets an attacker scan the server directly, look up other sites on the same IP, and map the target's infrastructure.

---

###  Task 4 — HTTP Header Inspection
**Goal:** Used to inspect/read HTTP response headers and identify server-side configurations and security-related headers, server banner, status, cookies and redirects.

$ curl -I https://networkwalks..

```bash
curl -I https://networkwalks.com
```

<div align="center">
  
<img width="974" height="402" alt="Curl-I" src="https://github.com/user-attachments/assets/b54f6483-b1dd-4722-80e5-72813cca3bba" />

📸 *Screenshot: curl output*

</div>

** How attackers use this:** Headers leak the web server, caching layer, and hidden API endpoints — giving fingerprinting clues without even loading the full page.

---

###  Task 5 — WAF Detection
**Goal:** Used to detect the presence of a Web Application Firewall (WAF) protecting the target application.

```bash
wafw00f networkwalks.com
```

<div align="center">

📸 *Screenshot: Wafw00f output*

<img width="644" height="430" alt="waf command" src="https://github.com/user-attachments/assets/bf6b3faf-32b7-4105-9d79-9b8ccfb0aa61" />

</div>

** How attackers use this:** wafw00f tells an attacker if a firewall is watching. Here the site behind ModSecurity(SpiderLabs). Knowing a WAF is present shapes the whole attack: naive attempts will be blocked 
or logged, so the attacker must adapt or try to bypass it.

--- 

###  Task 6 — DNS Enumeration
**Goal:** Used to enumerate DNS records such as NS, MX, TXT, SPF, and other publicly available DNS information.

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

*Made during the Networkwalks Cybersecurity & Ethical Hacking Internship*

</div>
