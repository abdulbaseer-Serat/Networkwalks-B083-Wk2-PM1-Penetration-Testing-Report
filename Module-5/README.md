<div align="center">

# Penetration Testing Report Module-4

### 🕸️ W2-PM4 — Footprinting & Reconnaissance Attacks with theHARVESTER

![Static Badge](https://img.shields.io/badge/Status-Completed-red)
![Static Badge](https://img.shields.io/badge/Module-W2--PM5-brightorange)
![Tool](https://img.shields.io/badge/tool-Zenmap%20%2F%20Nmap-orange)
![Platform](https://img.shields.io/badge/platform-Kali%20Linux-blueviolet)
![Static Badge](https://img.shields.io/badge/Purpose-Only%20for%20Education%20-blue)


</div>

---

## 📌 1. Project Title

**Network Scanning and Live Host Discovery Using Zenmap**

## 🎯 2. Objective

The objective of this project was to perform **network discovery** on a local network using **Zenmap**, the graphical interface for **Nmap**. The scan identified active hosts on the local subnet and collected their **IP** and **MAC addresses**.

The project also involved visualizing the discovered network using Zenmap's **Topology** feature and exporting the topology as a **PDF document**.

---

## 🛠️ 3. Tools and Environment Used

| Tool / Environment | Purpose |
|---|---|
| 🐉 **Kali Linux** | Operating environment (running inside VirtualBox) |
| 🖥️ **Zenmap** | Graphical interface for Nmap |
| 📡 **Nmap** | Underlying network scanning engine |
| 📦 **Oracle VirtualBox** | Virtualization platform |
| ⌨️ **Linux terminal commands** | Interface & file verification |
| 📄 **PDF viewer** | Verifying the exported topology |

---

## 🔬 4. Methodology

### Step 1 — Verify Zenmap Availability
Zenmap was already installed in the Kali Linux environment and was launched as the primary GUI for the scan. Since Zenmap runs Nmap under the hood, the generated scan command could be observed directly.

### Step 2 — Identify the Local IP Address & Network Interface

```bash
ip addr
```

| Property | Value |
|---|---|
| **Interface** | `eth0` |
| **IP Address** | `10.0.0.2/24` |
| **Broadcast Address** | `10.0.0.255` |
| **MAC Address** | `08:00:27:5a:87:bc` |

The `/24` CIDR notation identifies the subnet as `10.0.0.0/24` — selected as the scan target.

> **Local IP:** `10.0.0.2`  •  **Subnet:** `10.0.0.0/24`

### Step 3 — Configure the Network Scan in Zenmap

- **Target:** `10.0.0.0/24`
- **Profile:** `Ping Scan`
- **Generated Nmap command:**

```bash
nmap -sn 10.0.0.0/24
```

> `-sn` performs host discovery **without** a port scan.

### Step 4 — Perform Live Host Discovery

The Ping Scan was executed against the full subnet:

- **256** possible IP addresses scanned
- **2** hosts found up ✅

---

## 📊 5. Scan Results

| Host | IP Address | MAC Address |
|---|:---:|:---:|
| 🌐 Network Host / Gateway | `10.0.0.1` | `52:55:0A:00:00:01` |
| 🐉 Kali Linux Machine | `10.0.0.2` | `08:00:27:5A:87:BC` |

- `10.0.0.1` → active gateway device on the local virtual network
- `10.0.0.2` → the Kali Linux VM from which the scan was performed

---

## 🖨️ 6. Nmap Scan Output

```text
Nmap scan report for 10.0.0.1
Host is up.
MAC Address: 52:55:0A:00:00:01

Nmap scan report for 10.0.0.2
Host is up.

Nmap done: 256 IP addresses
2 hosts up
```

✅ Confirmed **two devices reachable** within the selected local network.

---

## 🗺️ 7. Network Topology Visualization

Zenmap's **Topology** feature was used to visualize the discovered network, displaying:

```
     Localhost
        │
   ┌────┴────┐
10.0.0.1   10.0.0.2
```

The visual representation showed the relationship between the discovered hosts and the scanning system, with both devices rendered as active nodes.

---

## 📤 8. Exporting the Network Topology

The topology was exported via Zenmap's **Save Graphic** option.

| Step | Command / Detail |
|---|---|
| Export filename | `network_topology.pdf` |
| Initial save location | `/root/network_topology.pdf` |
| Verify file exists | `sudo ls -l /root/network_topology.pdf` |
| Copy to user directory | `sudo cp /root/network_topology.pdf /home/kali/` |

The exported PDF was opened and verified — it contained the graphical topology showing both `10.0.0.1` and `10.0.0.2`.

---

## 💻 9. Commands Used

```bash
# Display network interface information
ip addr

# Display the system IP address
hostname -I

# Perform the Nmap ping scan (via Zenmap)
nmap -sn 10.0.0.0/24

# Verify the exported topology file
sudo ls -l /root/network_topology.pdf

# Locate the exported PDF
sudo find /root -name "network_topology.pdf"

# Copy the PDF to the Kali user directory
sudo cp /root/network_topology.pdf /home/kali/

# Verify the copied file
ls -l ~/network_topology.pdf
```

---

## 🔑 10. Key Findings

- ✅ Kali Linux machine IP: `10.0.0.2`
- ✅ Local subnet identified: `10.0.0.0/24`
- ✅ Ping Scan performed against the full subnet (**256** addresses scanned)
- ✅ **2 active hosts** discovered: `10.0.0.2` and `10.0.0.3`
- ✅ MAC address of `10.0.0.3` → `52:54:00:12:35:00`
- ✅ MAC address of Kali machine → `08:00:27:5A:87:BC`
- ✅ Network topology generated and exported as `network_topology.pdf`

---

## ✅ 11. Conclusion

This project demonstrated the process of performing **network discovery** and **live host identification** using Zenmap and Nmap.

The local network configuration was first identified using Linux networking commands, then the subnet `10.0.0.0/24` was scanned using Zenmap's **Ping Scan** profile. The scan successfully identified two active hosts — `10.0.0.2` and `10.0.0.3` — along with their IP and MAC address information.

Finally, Zenmap's **Topology** feature was used to visually map the discovered network, and the result was exported and verified as a PDF file.

**Skills practiced:**

- 🕵️ Network reconnaissance
- 📡 Local subnet identification
- 🖥️ Host discovery
- 📶 Nmap Ping Scanning
- 🖼️ Zenmap graphical interface
- 🌐 IP address identification
- 🔗 MAC address discovery
- 🗺️ Network topology visualization
- 📄 Exporting scan results for documentation

---

## 📸 12. Screenshots
<div align="center">
<img width="893" height="641" alt="ip addr" src="https://github.com/user-attachments/assets/6c318e92-9d25-4dc2-826d-74eb1fbb6d0f" />
</div>

<div align="center">
<img width="722" height="687" alt="ping scan" src="https://github.com/user-attachments/assets/d23c7a97-ea50-4025-b63b-0b1f7376664e" />
</div>

<div align="center">
<img width="888" height="737" alt="topology" src="https://github.com/user-attachments/assets/8e851a7a-66aa-44ce-91be-e5b37178974f" />
</div>

<div align="center">
<img width="884" height="733" alt="legend" src="https://github.com/user-attachments/assets/a56119a7-e9c4-4900-85f1-4231df77f2d7" />
</div>

<div align="center">
<img width="1292" height="865" alt="saving topology" src="https://github.com/user-attachments/assets/3a4d8c8c-8010-4c4d-a61c-9eaacd5a71f5" />
</div>

| # | Description | Suggested Filename |
|:---:|---|---|
| 1 | Zenmap application opened in Kali Linux | `zenmap-opened.png` |
| 2 | Network configuration via `ip addr` showing `10.0.0.2/24` | `ip-addr-output.png` |
| 3 | Zenmap target configured as `10.0.0.0/24`, Ping Scan profile selected | `scan-config.png` |
| 4 | Nmap command `nmap -sn 10.0.0.0/24` visible in Zenmap | `nmap-command.png` |
| 5 | Scan results showing 2 hosts up (`10.0.0.2`, `10.0.0.3`) + MAC info | `scan-results.png` |
| 6 | Zenmap Topology view with legend | `topology-view.png` |
| 7 | Exported `network_topology.pdf` opened successfully | `topology-pdf.png` |


---

## ⚠️ Disclaimer

> This project was performed for **educational purposes only**, scanning a **local, private virtual-lab subnet** (`10.0.0.0/24`) that the author owns and controls inside a personal VirtualBox environment. Never scan networks or hosts you do not own or have explicit written authorization to test.

---

<div align="center">

**Cybersecurity • Ethical Hacking • Network Scanning • Nmap/Zenmap**

</div>
