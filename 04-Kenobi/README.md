# 🖥️ Machine 04 — Kenobi

## 📌 Overview

Kenobi is a Linux machine focused on enumerating SMB and ProFTPD services, exploiting insecure configurations, and achieving privilege escalation through abuse of vulnerable SUID binaries.

---

## 🔍 Enumeration

### 🔸 Nmap Scan

nmap -sC -sV -p- -oN <machine>_nmap.txt <TARGET_IP>


### 🔸 Key Findings
- Service 1  
- Service 2  
- Potential vulnerabilities  
- OS fingerprint  

---

## 🛠️ Tools Used
- **Nmap** — Network scanning  
- **Enum4linux / SMBclient** — SMB enumeration  
- **Gobuster / FFUF** — Directory brute forcing  
- **Metasploit Framework** — Exploitation  
- **Impacket** — SMB/MSRPC interaction  
- **Netcat / Socat** — Shell handling  
- **LinPEAS / WinPEAS** — PrivEsc enumeration  
- **Custom scripts** — Auxiliary tooling  

---

## 🎯 Exploitation
Describe the vulnerability, exploitation path, payload, and how access was obtained.

Include:
- Commands  
- Output snippets  
- Reasoning behind each step  

---

## 🚀 Privilege Escalation
Explain how SYSTEM/root was achieved.

Include:
- Enumeration findings  
- Vulnerable services  
- Misconfigurations  
- Exploit or technique used  

---

## 📂 Loot & Flags
- User flag  
- Root/System flag  
- Additional artifacts  

---

## 🛡️ Defensive Takeaways
- Patch or mitigation  
- Hardening recommendations  
- Monitoring suggestions  
- Relevant logs or indicators  

---

## 🧠 Lessons Learned
- Key concepts reinforced  
- Mistakes corrected  
- Techniques improved  
- Notes for future machines
