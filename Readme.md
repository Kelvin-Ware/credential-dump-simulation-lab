# So You Want To Be A SOC Analyst – Lab Projects

This repository documents my hands-on labs from the course **"So You Want to Be a SOC Analyst"** by John Hammond. Each lab is based on real-world scenarios and includes defensive and offensive techniques, detection engineering, and practical SOC workflows.

---

## 🧪 Lab 1 – Credential Dumping

### 📝 Objective
Simulate a credential dumping attack using a Sliver implant and investigate the behavior using LimaCharlie and Sysmon logs.

---

### 🖥️ Environment

- **Attacker Machine:** Ubuntu Server (SSH)
- **Target Machine:** Windows 11 Pro VM
- **Tools Installed:**
  - Sysmon (via SwiftOnSecurity config)
  - LimaCharlie Sensor
  - Sliver C2 Framework

---

### 🛠️ Steps Taken

1. **Launched Sliver on Ubuntu Server**
   - Created implant
   - Transferred it to Windows target
   - Executed to establish callback

2. **Dumped Credentials on Target**
   - Used built-in Sliver modules (`minidump`, `procdump`)
   - Ran credential dumping from `C:\Users\localadmin\Downloads`

3. **Monitored Behavior**
   - Collected logs using **Sysmon** and **LimaCharlie**
   - Focused on process creation events, image loads, and command-line activity

---

### 🔍 Detection Engineering

- Confirmed event logs showing:
  - Sliver process launch (`sliver.exe`) from Downloads folder
  - Child process creation with access to LSASS
  - Use of dumping tools flagged in logs

---

### 🧠 Lessons Learned

- Process command-line arguments are critical for identifying malicious behavior
- Downloads folder should always be a high-suspicion launch point
- Credential dumping can be caught with proper Sysmon config and rule tuning

---

### 📁 Artifacts

> Add these later if you upload them:
- Screenshots of LimaCharlie detection
- Sysmon logs (redacted)
- IOC list or Sigma rules

---

### ✅ Status: Completed
