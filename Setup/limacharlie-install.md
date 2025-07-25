# Setup - Sysmon & LimaCharlie

## Windows Host
- Windows 11 Pro VM used
- Joined to LimaCharlie sensor via Windows x64 installer.

## LimaCharlie Sensor
- Sensor downloaded from LimaCharlie console.
- Installed with the appropriate Sensor Key.
- Confirmed successful connection via console.
![image alt](./Screenshots/Limacharlie sensor setup.png)

## Sysmon
- Installed Sysmon from official Sysinternals site.
- Used SwiftOnSecurity's sysmon-config:
  [https://raw.githubusercontent.com/SwiftOnSecurity/sysmon-config/master/sysmonconfig-export.xml]
- Applied config: .\sysmon64.exe -accepteula -i C:Windows\Temp\Sysmon\sysmonconfig.xml

