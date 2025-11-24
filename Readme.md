# 🔍 Task 1 — Basic Network Scanning with Nmap

This repository contains the deliverables for **Task 1: Basic Network Scanning with Nmap** as part of the Security Analyst Internship program.

---

## 📌 Objective
To perform a basic Nmap scan on a target virtual machine to identify:
- Open ports  
- Running services  
- Operating system information  

This task demonstrates foundational network reconnaissance skills used by both security analysts and penetration testers.

---

## 🛠️ Tools Used
- **Kali Linux (Attacker VM)**
- **Metasploitable 2 (Target VM)**
- **Nmap** — Network discovery and security auditing tool

---

## ⚙️ Nmap Command Used

```bash
nmap -O 10.140.18.85
```

**Flag Explanation:**
- `-O` → Enables OS detection
- Additional flags commonly used (optional):
  - `-sV` → Service version detection  
  - `-sC` → Default NSE scripts  
  - `-A` → Aggressive scan (OS + scripts + version)

---

## 📊 Scan Results (Summary)

Nmap identified multiple open ports and services on the target system, including:

| Port | Service        | Description |
|------|----------------|-------------|
| 21/tcp | ftp | File Transfer Protocol |
| 22/tcp | ssh | Secure Shell |
| 23/tcp | telnet | Insecure remote login |
| 25/tcp | smtp | Mail server |
| 80/tcp | http | Web server |
| 111/tcp | rpcbind | RPC service |
| 139/tcp | netbios-ssn | SMB service |
| 445/tcp | microsoft-ds | SMB over TCP |
| 3306/tcp | mysql | Database service |
| 5432/tcp | postgresql | Database service |
| 5900/tcp | vnc | Remote desktop |
| 6000/tcp | X11 | GUI server |
| ... | many more | Metasploitable intentionally exposes numerous services |

The target is running **Linux kernel 2.6.x**, which is consistent with Metasploitable2.

---

## 🕵️ Key Findings
- Metasploitable2 exposes **a large attack surface** with many open ports.  
- Services like **Telnet, FTP, RPC, MySQL, PostgreSQL, VNC**, etc., may allow exploitation.
- Several services run without encryption, making them vulnerable to sniffing or brute-force attacks.
- The system's outdated OS gives attackers multiple known vulnerabilities to exploit.

---

## 🔐 Security Recommendations
To secure a real-world system, the following steps are recommended:

- Disable or restrict unnecessary services.
- Replace insecure protocols like **Telnet** with **SSH**.
- Use firewalls to filter inbound connections.
- Restrict database access to localhost or internal networks.
- Keep OS and packages updated.
- Use strong authentication and SSH keys.

---

## 📁 Repository Contents

```
Task1-Nmap-Scan/
│── README.md
│── nmap_scan_results.txt
│── screenshots/
│      └── scan_output.png
```

---

## 📸 Screenshots

The Nmap scan screenshot is available in the **/screenshots/** directory.

---

## 📝 Raw Scan Output

Full raw scan results are available in:

```
nmap_scan_results.txt
```

---

## 🎯 Conclusion

This task demonstrates a complete basic Nmap scan used for initial reconnaissance in cybersecurity. It provides insight into open services, system exposure, and potential vulnerabilities of the target machine.

---

If you found this useful, feel free to ⭐ star the repository!
