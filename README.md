# 🔥 Task 4: Firewall Configuration (Windows)

## 🎯 Objective
To configure and test custom firewall rules on **Windows Defender Firewall**, understanding how it filters and controls network traffic across inbound and outbound connections.

---

## ⚙️ Steps Performed
1. **Viewed existing firewall rules**  
   - Opened the Windows Firewall Management Console using:
     ```
     wf.msc
     ```
   - Reviewed existing inbound and outbound rules to understand current configurations.

2. **Blocked inbound traffic on port 23 (Telnet)**  
   - Created a new **Inbound Rule** → Type: **Port (TCP)** → Specific Local Port: `23`  
   - Selected **Block the connection** and applied it to all profiles.  
   - Named the rule: `Block Telnet`.

3. **Allowed inbound traffic on port 22 (SSH)**  
   - Added another rule to **Allow TCP port 22** for secure shell access.

4. **Verified the rule using the Telnet client**  
   - Opened Command Prompt and tested:
     ```
     telnet 127.0.0.1 23
     ```
   - Received the response:
     ```
     Connecting to 127.0.0.1...
     Could not open connection to the host, on port 23: Connect failed
     ```
     confirming that Port 23 was successfully blocked.

5. **Removed the test rule**  
   - Deleted the temporary block rule after verification to restore default settings.

---

## 🧰 Tools Used
- **Windows Defender Firewall (Advanced Security)**
- **Command Prompt / PowerShell**
- **Telnet Client** (installed using `dism /online /Enable-Feature /FeatureName:TelnetClient`)

---

## 💡 Key Learnings
- Understood how **inbound** and **outbound** rules define network access control.
- Learned to use **port-based filtering** to secure the system against unauthorized access.
- Observed how blocking or allowing specific ports affects communication between applications and services.
- Gained insight into **real-time firewall testing** using the Telnet protocol.

---

## ✅ Outcome
Successfully configured and tested custom firewall rules to manage network traffic.
Confirmed that the Windows Firewall can effectively:
- Block unsafe connections (Telnet).
- Allow secure connections (SSH).
- Provide granular control over network access across **Domain**, **Private**, and **Public** profiles.

---

## 🧭 Command Summary
| Purpose | Command / Action |
|----------|------------------|
| Open Firewall Manager | `wf.msc` |
| Enable Telnet Client | `dism /online /Enable-Feature /FeatureName:TelnetClient` |
| Test Port 23 Connection | `telnet 127.0.0.1 23` |
| Verify Rule Removal | View **Inbound Rules** tab |

---

## 🔒 Conclusion
Through this task, the functioning of **Windows Defender Firewall** was explored in depth — learning how firewall rules protect a system by filtering network packets based on port, protocol, and profile.  
Practical testing with Telnet validated firewall enforcement, reinforcing the importance of rule-based network defense in system security.
