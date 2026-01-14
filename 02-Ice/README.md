# 🖥️ Machine 02 — Ice

## 📌 Overview
Ice is a beginner‑level TryHackMe machine that leverages a vulnerable Icecast service to gain 
RCE and escalate privileges on a Windows host.

---

## 🔍 Enumeration

### 🔸 Nmap Scan

```nmap -sS -sV -n -Pn -p- -oN scan.nmap 10.65.157.212```

Vuln confirmed 




### 🔸 Key Findings
- Icecast service running in port 8000  
- Vulnerability CVE-2004-1561    

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
