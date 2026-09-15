<div align="center">

# Penetration Testing Report Module-3

### 🕸️ W2-PM3 — Footprinting with Maltego

![Static Badge](https://img.shields.io/badge/Status-Completed-red)
![Static Badge](https://img.shields.io/badge/Module-W2--PM2-brightorange)
![Tool](https://img.shields.io/badge/tool-Maltego-purple)
![Platform](https://img.shields.io/badge/platform-Kali%20Linux-blueviolet)
![Static Badge](https://img.shields.io/badge/Purpose-Only%20for%20Education%20-blue)


</div>

---

## 📌 Objective

The objective of this project was to perform basic footprinting using **Maltego** and identify publicly available email addresses associated with the target domain.

> **Target Domain:** `networkwalks.com`

---

## 🛠️ Tools Used

| Tool | Purpose |
|------|---------|
| 🐉 **Kali Linux** | Penetration testing OS environment |
| 📦 **Oracle VirtualBox** | Virtualization platform for the Kali VM |
| 🔗 **Maltego Graph Desktop 4.12.1** | OSINT / footprinting & link-analysis tool |
| 🔍 **Search Engine Transform** | Discovers publicly indexed data tied to a domain |

---

## 📋 Tasks Performed

### Task 1 — Maltego Installation and Configuration
- install and Opened Maltego Graph Desktop within Kali Linux.
- Configured the application for footprinting activities.
- Verified successful initialization of the workspace.

### Task 2 — Email Address Discovery
- A **Domain** entity was added to the Maltego graph with the target: `networkwalks.com`
- The following transform was used:

```
[Utilities] To Emails @domain [Search Engine]
```

> This transform searches for publicly available email addresses associated with the specified domain.

---

## 🔄 Procedure

1. Opened **Maltego Graph Desktop**
2. Created a **new graph**
3. Added a **Domain entity**
4. Entered the target domain: `networkwalks.com`
5. Selected the Domain entity
6. Opened the available **transforms**
7. Searched for **email transforms**
8. Selected: `[Utilities] To Emails @domain [Search Engine]`
9. Ran the transform
10. Maltego processed the publicly available information and returned an associated email address

---

## 🔍 Result

| Target Domain | Discovered Email Address |
|:---:|:---:|
| `networkwalks.com` | `info@networkwalks.com` |

**Relationship discovered in Maltego:**

```
networkwalks.com
        │
        ▼
info@networkwalks.com
```

✅ The transform completed successfully and the email address was displayed as a new entity in the Maltego graph. The project task specifically required finding email addresses related to `networkwalks.com`.

---

## 📸 Screenshots
<img width="956" height="1031" alt="domain" src="https://github.com/user-attachments/assets/1c41c3f7-9204-4cb0-9282-5a1b9c7f61d6" />
<img width="961" height="1042" alt="step to run transformer" src="https://github.com/user-attachments/assets/a5117996-b8fb-438f-b406-6428203511ac" />
<img width="961" height="997" alt="search for email" src="https://github.com/user-attachments/assets/f9d713ad-86b1-4150-a764-16e28152d74f" />
<img width="962" height="1079" alt="results" src="https://github.com/user-attachments/assets/71dcc333-b86e-480d-9d96-910622bfd78b" />







| # | Description | Filename |
|:---:|---|---|
| 1 | Target domain `networkwalks.com` added as an entity | `domain-added.png` |
| 2 | Email transform `[Utilities] To Emails @domain [Search Engine]` selected | `email-transform.png` |
| 3 | Successful discovery: `networkwalks.com → info@networkwalks.com` | `email-discovered.png` |


## 🧠 Conclusion

This project demonstrated how **Maltego** can be used for footprinting and information gathering. A target domain was added as an entity, and a search-engine-based transform was executed to identify publicly available email addresses associated with that domain.

The email address **`info@networkwalks.com`** was successfully discovered for the target domain **`networkwalks.com`**, matching the educational task's expected result.

---

## ⚠️ Disclaimer

> This project was performed for **educational and authorized footprinting purposes only**. The target domain was used as part of the provided training task, which specifies that the activity should be performed with due permission.
>
> Do not run footprinting/OSINT transforms against domains you do not have authorization to test.

---

<div align="center">

**Cybersecurity • Ethical Hacking • OSINT • Footprinting**
