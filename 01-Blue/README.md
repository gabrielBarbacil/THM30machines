# 🟦 Machine 01 — Blue (TryHackMe)

## 📌 Overview
Blue is a Windows machine vulnerable to EternalBlue (MS17-010).  
The objective is to identify the SMB vulnerability, exploit it to gain a shell, and escalate privileges to obtain full system access.

---

## 🔍 1. Enumeration

### 🔸 Nmap Scan

nmap -sCV -n -Pn -p- -oN scan.nmap <TARGET_IP>

---

### 🔸 Key Findings
- SMB (port 445) open  
- Potential MS17-010 vulnerability  
- Windows 7 / Server 2008 R2 fingerprint  

---

## 🛠️ 2. Tools Used

These are the primary tools and utilities used during the assessment of this machine:

- **Nmap** — Network scanning and service enumeration  
- **SMBclient** — SMB enumeration and information gathering  
- **Metasploit Framework** — Exploitation and payload handling  
- **Impacket Suite** — SMB/MSRPC interaction and validation  
- **Netcat / Socat** — Shell handling and reverse connections  
- **PowerShell / CMD** — Windows post‑exploitation commands  
- **LinPEAS / WinPEAS** — Privilege escalation enumeration (when applicable)  
- **Custom scripts** — Auxiliary enumeration or exploitation helpers  

---

## 🎯 3. Exploitation

### 🔸 EternalBlue (MS17-010)
- Vulnerability confirmed
  ![Confirmed](../Images/01-Blue/vulnConfirmed.png)
- Use a modern exploit module or manual approach  
- flag2.txt is in the sam location    

---

## 🚀 4. Privilege Escalation
Since EternalBlue grants SYSTEM, no additional escalation is required.  
Document post-exploitation steps and verification commands.

---

## 📂 5. Loot & Flags
- User flag  
- Root/System flag  
- Any additional artifacts  

---

## 🛡️ 6. Defensive Takeaways
- Disable SMBv1  
- Apply MS17-010 patch  
- Monitor anomalous SMB traffic  
- Harden legacy Windows systems  

---

## 🧠 7. Lessons Learned
- Importance of patch management  
- EternalBlue exploitation workflow  
- SMB enumeration methodology  
- Windows post-exploitation basics  

---

## 📚 References
- TryHackMe: Blue  
- Microsoft MS17-010 advisory  
- EternalBlue exploit documentation  
