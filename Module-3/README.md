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

This project demonstrates basic footprinting and Open Source Intelligence (OSINT) techniques using **Maltego**.

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

### Task 1 — Maltego Installation and Configuration. 
- Install and configure Maltego Graph Desktop within Kali Linux. 
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

1. Launch **Maltego Graph Desktop**
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
<img width="956" height="867" alt="01-target-domain" src="https://github.com/user-attachments/assets/b498d614-4825-4f72-aca7-d913af1a9173" />
<div align="center">

📸 *Screenshot: 01-domain-entity*

</div>
        
<img width="961" height="879" alt="02-email-transform" src="https://github.com/user-attachments/assets/a3d4d04c-80c6-47e0-a132-2511cf7b0b6c" />
<div align="center">

📸 *Screenshot: 02-email-transform*

</div>
<img width="961" height="872" alt="03-email-search" src="https://github.com/user-attachments/assets/20139e90-5265-4b6c-991b-eec7ec6d4373" />
<div align="center">

📸 *Screenshot: 03-email-search*

</div>
<img width="962" height="917" alt="04-email-discovered" src="https://github.com/user-attachments/assets/7dc09a32-9800-4017-bec2-a7324620a4dd" />
<div align="center">

📸 *Screenshot: 04-email-discovered*

</div>




| # | Description | Filename |
|:---:|---|---|
| 1 | Target domain `networkwalks.com` added as an entity | `01-domain-entity.png` |
| 2 | Selected Email Discovery Transform | `02-email-transform.png` |
| 3 | Executed Email Search Transform | `03-email-search.png` |
| 3 | Email Address Successfully Discovered: `networkwalks.com → info@networkwalks.com` | `email-discovered.png` |


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
