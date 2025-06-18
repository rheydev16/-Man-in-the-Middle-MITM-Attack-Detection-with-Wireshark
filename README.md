# 🔍Man-in-the-Middle-MITM-Attack-Detection-with-Wireshark
This project demonstrates how to detect a **Man-in-the-Middle (MITM)** attack using **Wireshark** and ARP poisoning analysis. It was created for internship learning purposes and showcases hands-on skills in network security monitoring and traffic analysis.

---

## 📌 Project Purpose

The main purpose of this project is to understand how MITM attacks work and how to detect them using Wireshark. By simulating a real MITM attack using Ettercap, I learned how to identify signs of ARP poisoning on the network and configure Wireshark profiles for efficient monitoring.

---

## ⚙️ Tools & Setup

- **Kali Linux (VirtualBox)** — Used to run the MITM attack with Ettercap.
- **Ettercap** — Tool for performing the MITM attack via ARP poisoning.
- **Windows 10** — The target machine for the attack.
- **Wireshark** — Used on the victim/monitoring system to detect the attack.
- **Custom Wireshark Profile** — Contains filters for detecting ARP spoofing patterns.

---

## 🧪 Project Setup

1. **Environment Configuration**:
   - Kali Linux and Windows 10 machines are on the same network.
   - Kali is running on VirtualBox with bridged or NAT adapter.
   - Windows 10 is the target of the MITM attack.

2. **MITM Attack Simulation**:
   - On Kali Linux:
     ```bash
     sudo ettercap -G
     ```
   - Targeted both gateway and Windows machine using ARP poisoning.

3. **Detection with Wireshark**:
   - Wireshark is running on the Windows machine.
   - A custom Wireshark profile named `MITM Detection` is used.
   - The filter applied:
     ```wireshark
     arp.dst.proto_ipv4 == <target_ip> && arp.src.hw_mac != <original_mac>
     ```
   - This filter helps detect ARP replies with mismatched MAC addresses.

---
## 📁 File Structure

```text
├── screenshots/
│ ├── filter-setup.png # Wireshark ARP filter setup screenshot
│ └── mitm-detected.png # Traffic showing MITM attack detected
├── README.md # Project documentation
```

---

## 📸 Screenshots

### 🖼️ Wireshark Filter Setup
> Shows the custom filter used to detect ARP poisoning.

![Wireshark Filter Setup](./screenshots/filter-setup.png)

---

### 🖼️ MITM Attack Detected
> A captured example of an ARP reply with a spoofed MAC address.

![MITM Detected](./screenshots/mitm-detected.png)

---


