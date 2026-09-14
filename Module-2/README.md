<div align="center">

#  Penetration Testing Report Module-2

### Footprinting & Reconnaissance Attacks With Google Hacking Database - GHDB

![Static Badge](https://img.shields.io/badge/Status-Completed-red)
![Static Badge](https://img.shields.io/badge/Module-W2--PM2-brightorange)
![Static Badge](https://img.shields.io/badge/Tool-Google%20Hacking%20Database--GHDB-orange)
![Static Badge](https://img.shields.io/badge/Purpose-Only%20for%20Education%20-blue)


</div>

---

## 📖 Background

**GHDB (Google Hacking Database)** is a large collection of ready-made search queries called **Google dorks**. These dorks use normal Google search operators in clever ways to surface information that a website has unintentionally left public — exposed camera feeds, open directories, login pages, config files, and documents.

GHDB was built for pentesters and security researchers so they can find and fix these leaks. It's hosted on [exploit-db.com](https://www.exploit-db.com/google-hacking-database).

## 🎯 What this project does

Using **GHDB dorks**, this module footprints public targets through **Google alone** — without ever directly contacting a device. Each result was opened, verified, and recorded together with the exact dork used.

---

## 🧩 Methodology

1. Open [exploit-db.com](https://www.exploit-db.com) → **GHDB**
2. Search for a relevant keyword (e.g. `cam`, `index of pdf`)
3. Copy a candidate dork
4. Run the dork directly in Google
5. Open each result and **verify** it's genuinely live / relevant
6. Record the link + dork used in the tables below

---

## 📷 Task 1 — Live Exposed Security Cameras

> **Goal:** Find 10x live vulnerable security camera links exposed & accessible from the internet.

> ⚠️ **Note on scope:** Several results returned during this search pointed to live feeds **inside private residences** (e.g. someone's living room). Those are **deliberately excluded** from this report — publishing working links to unauthenticated cameras inside private homes is a real privacy/safety risk, and it's outside the point of the exercise. Only feeds pointed at **public or commercial spaces** are listed. Remaining rows are left for you to complete after independently verifying the feed is genuinely public-facing (municipal/tourism webcam, storefront, etc.) — not a private home.

| No. | Link                                                        | Relevant Dork                                | Username / Password |
| :-: | ----------------------------------------------------------- | -------------------------------------------- | :-----------------: |
|  1  | `http:/109.233.191.130:8080/`                               | `intitle:"webcamXP" inurl:8080`              |         ---         |
|  2  | `http://74.105.120.201:444/home.html`                       | `intitle:"webcamXP 5" inurl:admin.html`  |         ---         |
|  3  | `http://50.184.100.116:8000/index.html`                     | `intitle:"webcamXP" inurl:8000 "JavaScript"` |         ---         |
|  4  | `http://cbsouthmetro.ddns.net:8080/`                        | `intitle:"AXIS" "Live View" inurl:view`      |         ---         |
|  5  | `http://webcam.hunderdorf.de/`                              | `"webcam" "Live View" "Setup" "Help"`        |         ---         |
|  6  | `http://117.5.117.199:43/`                                  | `product:"Hikvision IP Camera"`              |         ---         |
|  7  | `http://72.199.200.5:8080/`                                 | `intitle:"webcamXP 5" inurl:8080`            |         ---         |
|  8  | `http://55.84.108.128:8080/`                                | `intitle:"WEBCAMXP 5" "Live View"`           |         ---         |
|  9  | `http://72.199.200.5:8080/`                                 | `intitle:"webcamXP" "Not logged in"`         |         ---         |
|  10 | `http://55.84.108.128:8080/`                                | `intitle:"webcamXP" inurl:8080 "Source"`     |         ---         |


---

## 📚 Task 2 — Downloadable Mathematics eBooks (PDF)

> **Goal:** Find 10x listings which contain downloadable mathematics ebooks in PDF format.

| No. | Link | Relevant Dork |
|:---:|------|----------------|
| 1 | http://erewhon.superkuh.com/library/Math/ | `intitle:index.of "parent directory" mathematics pdf` |
| 2 | [hlevkin.com/.../Math/Gardner/](https://hlevkin.com/hlevkin/90MathPhysBioBooks/Math/Gardner/) | `intitle:index.of "parent directory" mathematics pdf` |
| 3 | [easyteacherworksheets.com/pages/pdf/math/](https://easyteacherworksheets.com/pages/pdf/math/) | `intitle:index.of "index of" math pdf` |
| 4 | [education.giakonda.org.uk/Maths/](https://education.giakonda.org.uk/Maths/) | `intitle:index.of "parent directory" mathematics pdf` |
| 5 | [math.mcgill.ca/barr/](https://math.mcgill.ca/barr/) | `intitle:"index of pdf files" mathematics` |
| 6 | [lira.epac.to/DOCS-TECH/Math/Algebra & Trigonometry/](https://lira.epac.to/DOCS-TECH/Math/Algebra%20&%20Trigonometry/) | `intitle:index.of "parent directory" mathematics pdf` |
| 7 | [sci.brooklyn.cuny.edu/~mate/misc/](https://sci.brooklyn.cuny.edu/~mate/misc/) | `intitle:index.of "parent directory" mathematics pdf` |
| 8 | [sajaipuriacollege.ac.in/pdf/pdf/MATHEMATICS/](https://sajaipuriacollege.ac.in/pdf/pdf/MATHEMATICS/) | `intitle:index.of "index of" mathematics pdf` |
| 9 | [file.helpstudentpoint.com/wp-content/uploads/2024/04/](https://file.helpstudentpoint.com/wp-content/uploads/2024/04/) | `intitle:index.of mathematics pdf` |
| 10 | [erewhon.superkuh.com/library/Math/](https://erewhon.superkuh.com/library/Math/) | `intitle:"index of" "library/Math" pdf` |

*(Username/Password: `---` for all — these are open directory listings, no auth required.)*

---

## 🧠 Extra Reference Dorks

Additional webcam-related dorks worth practicing to extend this exercise:

```
allintitle: "Network Camera NetworkCamera"
intitle:"EvoCam" inurl:"webcam.html"
intitle:"Live View / - AXIS"
intitle:"LiveView / - AXIS" | inurl:view/view.shtml
inurl:indexFrame.shtml "Axis Video Server"
inurl:axis-cgi/jpg
inurl:"MultiCameraFrame?Mode=Motion"
inurl:/view.shtml
inurl:/view/index.shtml
"my webcamXP server!"
```

Exploit-DB also lists many current exploits worth studying to improve your knowledge — see the **Exploits** tab on [exploit-db.com](https://www.exploit-db.com).

---

## 🔍 Why GHDB Matters in Footprinting

Reconnaissance is the first stage of every real attack. Before touching a target, an attacker builds a full picture of it using only **public information** — and Google is one of the richest sources of that information. GHDB turns ordinary Google searches into a precise recon tool that surfaces exposed cameras, open folders, backup files, login portals, and leaked documents that owners never meant to publish.

Because all of this comes straight from Google, the target is never directly contacted — which makes GHDB one of the **quietest and hardest-to-detect** forms of footprinting.

The same dorks an attacker uses to find weaknesses are also used by **defenders** to audit their own domains, so they can discover what they're leaking and lock it down before someone else finds it.

---

## ⚠️ Liability Disclaimer

> These materials are for **education and research purposes only**. Although this project includes practical labs, they are meant strictly for learning. The aim is to show how attacks work in real-world systems so they can be defended better.
>
> **Do not use anything from this repository to break the law.** The author is not responsible for what you do with this knowledge. Every action you take is your own responsibility. Misuse can lead to criminal charges, heavy fines, loss of employment, and a permanent record. **Unauthorised access is a crime in most countries even when nothing is damaged.**

**Hacking is only legal when:**

- ✅ You test a device or network that you own, or your lab environment
- ✅ You have written and documented permission from the owner
- ✅ You are working as a security professional under a signed agreement with an agreed scope

**Everything outside these cases is illegal.**

---

<div align="center">

*By using this repository you confirm that you have read this disclaimer and accept full responsibility for your actions.*


</div>
