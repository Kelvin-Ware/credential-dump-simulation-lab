# 🛠️ Setup – Sysmon & LimaCharlie

This section documents the setup process for monitoring tools used in the lab: Sysmon and the LimaCharlie EDR sensor.

---

## 🪟 Windows Host

- Windows 11 Pro virtual machine was used.
- Joined to LimaCharlie via the Windows x64 sensor installer.

---

## 🌐 LimaCharlie Sensor

- Sensor downloaded from the LimaCharlie console.
- Installed using the appropriate Sensor Key.
- Verified successful connection via the LimaCharlie console.

📸 [LimaCharlie Install](./Screenshots/limacharlie%20install.png)  
📸 [Sensor Setup](./Screenshots/Limacharlie%20sensor%20setup.png)  
📸 [Connection Verification](./Screenshots/Verify%20limacharlie%20connection.png)

---

## ⚙️ Sysmon

- Downloaded and installed Sysmon from the official Sysinternals site.
- Used the SwiftOnSecurity configuration for enhanced visibility.

Sysmon config used:  
```
Invoke-WebRequest -Uri https://raw.githubusercontent.com/SwiftOnSecurity/sysmon-config/master/sysmonconfig-export.xml -Outfile C:\Windows\Temp\Sysmon\sysmonconfig.xml
```

Command to install and apply configuration:
```
.\sysmon64.exe -accepteula -i C:\Windows\Temp\Sysmon\sysmonconfig.xml
```

📸 [Sysmon Install](./Screenshots/Sysmon-Install.png)  
📸 [Applied SwiftOnSecurity Config](./Screenshots/Sysmon%20SwiftOnSecurity%20Config.png)  
📸 [Verify Sysmon is Running](./Screenshots/Sysmon-Running.png)
