<div align="center">

# Penetration Testing Report Module-4

### 🕸️ W2-PM4 — Footprinting & Reconnaissance Attacks with theHARVESTER

![Static Badge](https://img.shields.io/badge/Status-Completed-red)
![Static Badge](https://img.shields.io/badge/Module-W2--PM4-brightorange)
![Tool](https://img.shields.io/badge/tool-theHarvester-orange)
![Platform](https://img.shields.io/badge/platform-Kali%20Linux-blueviolet)
![Static Badge](https://img.shields.io/badge/Purpose-Only%20for%20Education%20-blue)


</div>

---

## 📌 Objective

This module focused on performing footprinting and reconnaissance using **theHarvester**, an information-gathering tool available in Kali Linux.

The main objective was to collect publicly available information related to the target organization **ABC**, by searching for information associated with the domain:

> **Target Domain:** `microsoft.com`

Activities were divided into two tasks:

1. Gathering information using the **Baidu** data source
2. Gathering information using **all available/configured sources**


theHarvester identifies publicly available information such as email addresses, hosts, and subdomains related to a target domain by pulling from public sources like search engines and other OSINT data sources.
---

## 🎯 2. Objective

- Identify email addresses associated with the target domain
- Discover hosts and subdomains related to the target organization
- Understand how different data sources affect the amount of information collected
- Compare results from a single source vs. results from multiple sources

---

## 🛠️ 3. Environment and Tool Used

| Component | Details |
|---|---|
| 🐉 **Operating System** | Kali Linux |
| 🔎 **Tool Used** | theHarvester |
| 🎯 **Target Domain** | `microsoft.com` |

theHarvester was already available in the Kali Linux environment and was executed through the terminal.

---

## 📖 4. Background

Footprinting is an important reconnaissance phase in which publicly available information about a target organization is collected.

theHarvester automates the process of gathering information from various public sources. Depending on the selected data source and API access, it can return:

- 📧 Email addresses
- 🖥️ Hosts
- 🌐 Subdomains
- 🧾 IP-related information
- 🧑 Names or other publicly available information

Two searches were performed against `microsoft.com` to compare a single-source search vs. a multi-source search.

---

## 🧪 5. Task 1 — Footprinting Using Baidu

**Objective:** Search for email addresses and subdomains/hosts associated with `microsoft.com` using **Baidu** as the data source.

```bash
theHarvester -d microsoft.com -l 1000 -b baidu
```

| Flag | Meaning |
|:---:|---|
| `-d microsoft.com` | Target domain to investigate |
| `-l 1000` | Result limit |
| `-b baidu` | Data source used → **Baidu** |

### 🔄 Procedure
1. Opened the Kali Linux terminal
2. Executed theHarvester against the target domain
3. Used Baidu as the selected data source, with a result limit of 1000
4. Saved the output to a text file:
   ```bash
   theHarvester -d microsoft.com -l 1000 -b baidu > task1-results.txt
   ```
5. Displayed the saved results:
   ```bash
   cat task1-results.txt
   ```

### ✅ Results

**Email Addresses Found (9):**
```
contact@microsoft.com
support@microsoft.com
abc@microsoft.com
info@microsoft.com
mscomblg@microsoft.com
partnerhubsupport@microsoft.com
postmaster@microsoft.comservice.microsoft.com
user@contoso.onmicrosoft.com
viva-noreply@microsoft.com
```

**Hosts Found (28):**
```
2fsupport.microsoft.com
account.microsoft.com
activation.sls.microsoft.com
admin.microsoft.com
adoption.microsoft.com
demo.wd.microsoft.com
developer.microsoft.com
docs.microsoft.com
foundershub.startups.microsoft.com
go.microsoft.com
graph.microsoft.com
hxd.research.microsoft.com
```

theHarvester successfully gathered publicly available email and host information using only the Baidu data source.

---

## 🧪 6. Task 2 — Footprinting Using All Sources

**Objective:** Perform information gathering against the same target using **all available/configured sources**.

```bash
theHarvester -d microsoft.com -l 50 -b all
```

| Flag | Meaning |
|:---:|---|
| `-d microsoft.com` | Target domain |
| `-l 50` | Result limit |
| `-b all` | Attempt searches across **all supported/configured sources** |

### 🔄 Procedure
1. Opened the Kali Linux terminal
2. Executed theHarvester against `microsoft.com` with `-l 50 -b all`
3. Observed API key warnings for sources requiring authentication
4. Observed searches being performed against accessible sources
5. Saved the output to a text file:
   ```bash
   theHarvester -d microsoft.com -l 50 -b all > task2-results.txt
   ```
6. Displayed the saved results:
   ```bash
   cat task2-results.txt
   ```

### 🔑 API Key Messages

Several sources displayed "missing API key" warnings, e.g.:

```
[!] Missing API key for Shodan.
[!] Missing API key for Hunter.
```

Sources affected included: `BeVigil`, `Bitbucket`, `BuiltWith`, `Brave Search`, `Censys`, `CriminalIP`, `DNSDumpster`, `GitHub`, `HaveIBeenPwned`, `Hunter`, `IntelX`, `Netlas`, `Shodan`, `VirusTotal`, `WhoisXML`, `ZoomEye`.

> ℹ️ These warnings do **not** mean the scan failed — theHarvester continued searching all sources that didn't require missing credentials, e.g.:
> ```
> [*] Searching Chaos.
> [*] Searching Baidu.
> [*] Searching Certspotter.
> [*] Searching Duckduckgo.
> ```

### ✅ Results

A **significantly larger** collection of Microsoft-related hosts and subdomains was returned, since multiple sources were queried:

```
webmail.microsoft.com
westcentralus.api.cognitive.microsoft.com
westus.api.cognitive.microsoft.com
windows.licensing.commerce.microsoft.com
wwwbeta.microsoft.com
wwwqa.microsoft.com
yourchoice.microsoft.com
```

Some entries included IP/hostname resolution info:

```
webpa201.int.aeos.microsoft.com:207.68.147.103
webpa202.int.aeos.microsoft.com:207.68.147.104
```

---

## ⚖️ 7. Comparison — Task 1 vs. Task 2

| Feature | Task 1 | Task 2 |
|---|:---:|:---:|
| **Target** | microsoft.com | microsoft.com |
| **Data Source** | Baidu | All available/configured sources |
| **Result Limit** | 1000 | 50 |
| **Emails Found** | 2 | Multi-source collection attempted |
| **Hosts/Subdomains** | 10 | Significantly larger result set |
| **API Keys Required** | None (Baidu) | Several sources required keys |
| **Search Scope** | Single source | Multiple sources |

---

## 🧠 8. Key Learning

The **data source selected significantly affects the information collected**:

- `-b baidu` → limits the search to a single source
- `-b all` → attempts searches across every supported/configured source

However, some sources require **API keys** — so the amount of information successfully collected depends on:

- The selected data source(s)
- API key availability
- Source accessibility
- Current availability of publicly indexed information

> 💡 Results may also differ over time, since information sources and their indexing algorithms change.

---

## 📸 9. Screenshots
## 📸 Screenshots

| # | Description | Filename |
|:---:|---|---|
| 1 | Displaying theHarvester help menu and reviewing supported command-line options, parameters, and OSINT data sources available for reconnaissance activities. | `01-theharvester-help-menu.png` |
| 2 | Task 1: Executing theHarvester against `microsoft.com` using the Baidu search engine source with a result limit of 1000. | `02-baidu-search-command.png` |
| 3 | Task 1: Reviewing the harvested email addresses and discovered hosts retrieved from Baidu search results and saved to the output file. | `03-task1-saved-results.png` |
| 4 | Task 2: Executing theHarvester against `microsoft.com` using all available OSINT data sources (`-b all`) with a result limit of 50. | `04-all-sources-command.png` |
| 5 | Task 2: Reviewing reconnaissance results collected from multiple public intelligence sources, including discovered email addresses, hosts, and subdomains related to Microsoft. | `05-all-sources-results.png` |


---

## ✅ 10. Conclusion

This module successfully demonstrated the use of **theHarvester** for basic footprinting and reconnaissance.

In **Task 1**, theHarvester was used with the Baidu data source and returned **2 email addresses** and **10 hosts** for `microsoft.com`.

In **Task 2**, theHarvester was executed using all available/configured sources. Several sources required API keys and could not be accessed without credentials, while other accessible sources continued to provide information — resulting in a **much larger collection** of Microsoft-related hosts and subdomains.

Overall, the module demonstrated how theHarvester automates the collection of publicly available information, and how the choice of data source(s) directly affects the breadth of results obtained during footprinting and reconnaissance.

---

## ⚠️ Disclaimer

> This project was performed for **educational and authorized footprinting purposes only**, using a well-known public organization's domain as a training target. Only publicly indexed / OSINT information was collected — no systems were directly accessed or exploited.

---

<div align="center">

**Cybersecurity • Ethical Hacking • OSINT • Footprinting**

⭐ If you found this repository useful, consider starring it.

</div>
