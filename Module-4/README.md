<div align="center">

# Penetration Testing Report Module-4

### 🕸️ W2-PM4 — Footprinting & Reconnaissance Attacks with theHARVESTER

![Static Badge](https://img.shields.io/badge/Status-Completed-red)
![Static Badge](https://img.shields.io/badge/Module-W2--PM4-brightorange)
![Tool](https://img.shields.io/badge/tool-theHarvester-orange)
![Tool](https://img.shields.io/badge/tool-Maltego-purple)
![Platform](https://img.shields.io/badge/platform-Kali%20Linux-blueviolet)
![Static Badge](https://img.shields.io/badge/Purpose-Only%20for%20Education%20-blue)


</div>

---

## 📌 Objective

This lab demonstrates passive reconnaissance and footprinting using theHarvester.

The objective was to discover publicly available:

- Email addresses
- Subdomains
- Hosts

associated with the target domain.

### Target Domain

```text
microsoft.com
```

---

## 🛠 Tools Used

| Tool | Purpose |
|--------|---------|
| Kali Linux | Security testing platform |
| theHarvester | Passive OSINT and reconnaissance tool |
| Baidu Search Engine | Public data source |
| Multiple OSINT Sources | Broader data collection |

---

## 📋 Tasks Performed

### Task 1

Discover email addresses and subdomains associated with:

```text
microsoft.com
```

Using:

```bash
theHarvester -d microsoft.com -l 1000 -b baidu
```

---

### Task 2

Discover email addresses and subdomains using all available sources.

```bash
theHarvester -d microsoft.com -l 50 -b all
```

---

## 🔄 Procedure

### Task 1

1. Open theHarvester in Kali Linux
2. Review available options
3. Execute:

```bash
theHarvester -d microsoft.com -l 1000 -b baidu
```

4. Analyze harvested information
5. Save results

---

### Task 2

1. Open a new terminal
2. Execute:

```bash
theHarvester -d microsoft.com -l 50 -b all
```

3. Review discovered assets
4. Export findings

---

## 📸 Screenshots

### Launching theHarvester

![Launching theHarvester](screenshotsg

<div align="center">

📸 *Screenshot: Launching theHarvester in Kali Linux*

</div>

---

### Usage Instructions

![Help Menu](screenshots/menu.png

<div align="center">

📸 *Screenshot: theHarvester Usage Instructions*

</div>

---

### Baidu-Based Harvesting

![Baidu Query](screenshots/03-baidu-search-command.png)

er">

📸 *Screenshot: Executing Baidu-Based Harvesting Query*

</div>

---

### Baidu Results

![Baidu Results](screenshots/04-baidu- align="center">

📸 *Screenshot: Email Addresses and Subdomains Discovered via Baidu*

</div>

---

### All Sources Query

![All Sources Query](screenshots/05-ng

<div align="center">

📸 *Screenshot: Executing All Sources Harvesting Query*

</div>

---

### All Sources Results

screenshots/06-all-sources-results.png

<div align="center">

📸 *Screenshot: Results Collected from Multiple Public Sources*

</div>

---

## 🧠 Skills Demonstrated

- OSINT
- Footprinting
- Passive Reconnaissance
- Information Gathering
- Subdomain Enumeration
- Email Enumeration
- Kali Linux
- Security Documentation

---

## 🔍 Key Concepts Learned

### Passive Reconnaissance

theHarvester gathers information from publicly available sources without directly interacting with the target infrastructure.

### Email Enumeration

Publicly exposed email addresses can help defenders identify information leakage risks.

### Subdomain Discovery

Subdomains increase an organization's attack surface and should be continuously monitored by security teams.

---

## 📂 Repository Structure

```text
footprinting-with-theharvester/
│
├── README.md
├── report/
│   └── W2-PM4-Footprinting-With-theHarvester.pdf
│
└── screenshots/
    ├── 01-theharvester-launch.png
    ├── 02-tool-help-menu.png
    ├── 03-baidu-search-command.png
    ├── 04-baidu-results.png
    ├── 05-all-sources-command.png
    └── 06-all-sources-results.png
```

---

## ⚠️ Disclaimer

This project was performed in a controlled educational environment for learning and defensive security awareness.

All information was obtained from publicly available sources. Always obtain proper authorization before performing reconnaissance or security testing activities.

---

<div align="center">

### Cybersecurity • Ethical Hacking • OSINT • Footprinting

⭐ If you found this repository useful, consider starring it.

</div>
