# Credential Dump Simulation Lab

## Overview

This lab simulates credential dumping techniques on a Windows 11 Pro VM using Sliver C2 implants. The objective is to emulate attacker behavior, monitor endpoint telemetry with Sysmon, and develop detection strategies with LimaCharlie.

---

## Lab Setup

- **Attack Server:** Ubuntu Server running Sliver C2  
- **Target Endpoint:** Windows 11 Pro virtual machine  
- **Tools:** Sysmon for detailed logging, LimaCharlie for cloud-based telemetry and detection

---

## Attack Simulation Steps

1. Deployed Sliver implant to the Windows VM via SSH from the Ubuntu attack server.  
2. Installed and configured Sysmon on the Windows endpoint to capture detailed process and network events.  
3. Configured LimaCharlie sensor on the Windows VM for remote monitoring and alerting.  
4. Executed credential dumping commands such as `procdump` and `MiniDump` targeting LSASS memory to simulate attacker tactics.

---

## Detection & Analysis

- Collected Sysmon logs to identify suspicious processes and command-line activity.  
- Created detection rules within LimaCharlie to alert on typical credential dumping behavior.  
- Monitored alerts and verified detection efficacy during simulated attacks.

---

## Learnings

- Gained hands-on experience with adversary emulation using Sliver.  
- Improved understanding of how Sysmon logs capture attacker behavior.  
- Practiced detection rule creation and tuning in LimaCharlie.

---

## Next Steps

- Expand lab with additional attack techniques.  
- Automate response workflows based on detection alerts.  
- Integrate YARA rules to detect malicious implants and scripts.

---

Feel free to explore this repo and reach out with any questions!
