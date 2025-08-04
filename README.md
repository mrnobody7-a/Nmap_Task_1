# 🔍 Nmap Scan & Wireshark Analysis Report

## 🧠 Objective
Understand network exposure by discovering open ports on devices within a local network using Nmap. Wireshark is optionally used to analyze the traffic generated during scanning.

---

## 🛠️ Tools Used
- [Nmap](https://nmap.org/download.html) – Network scanner
- Wireshark (optional) – Packet analysis tool

---

## 🧭 Steps Performed

### 1. Install Nmap
Download and install from the official site:  
👉 https://nmap.org/download.html

---

### 2. Identify Local IP Range
Use the following commands to find your IP range:

- **Windows**:  
  ```bash
  ipconfig


* **Linux**:

  ```bash
  ifconfig
  ```

  or

  ```bash
  ip addr
  ```

Example IP Range: `192.168.1.0/24`

---

### 3. Perform TCP SYN Scan

Run a stealth scan on a target IP:

```bash
nmap -sS 45.33.32.156
```

---

### 4. Example Scan Output

```
Host: 192.168.1.10
Open Ports:
- 80 (HTTP)
- 22 (SSH)
```

---

### 5. Wireshark Packet Capture (Optional)

Captured packets during the scan show SYN, SYN-ACK, and RST packets indicating the state of the ports.

---

## ⚙️ Common Ports & Services

| Port | Service | Description                   |
| ---- | ------- | ----------------------------- |
| 80   | HTTP    | Web server, unencrypted       |
| 22   | SSH     | Remote access, secure channel |

---

## ⚠️ Security Risks

* **Port 80 (HTTP)**: Data is unencrypted, making it vulnerable to sniffing.
* **Port 22 (SSH)**: Susceptible to brute-force attacks if weak credentials are used.

---

## 💾 Saving Results

Export scan results for reporting:

* **Text Output**: `nmap -sS 45.33.32.156 -oN scan.txt`
* **HTML Output**: `nmap -sS 45.33.32.156 -oX scan.xml && xsltproc scan.xml -o scan.html`


```
