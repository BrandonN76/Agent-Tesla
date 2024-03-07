## Malware Analysis
### Agent Tesla Family

#### Lab Description:
In this analysis, I'll be examining 'akhx.exe,' a malware sample associated with the notorious Agent Tesla malware family. I will be performing static and dynamic analysis of the malware to get a better understanding of the malware’s characteristics, functionality, and potential impact on the compromised system.

#### Static Analysis

**VirusTotal Report:**
<img src="https://i.imgur.com/3E1q2EO.png">
Hashes:  
- MD5: 93cd95cbafbef5c843087bb24f6453f9  
- SHA-1: a8cd16431992c505c454a42fd7519fa8f98332a9  
- SHA-256: 566a9b82252b4402d80e3cf288a9ff19648b2f856c385c1ec9ea13041ad5787d

Original File name: akhx.exe  
Presented File Name: 566a9b82252b4402d80e3cf288a9ff19648b2f856c385c1ec9ea13041ad5787d.exe  
File Size: 591872 bytes  
File Type: PE32  
DLL: mscoree.dll

Notable Strings:  
- ConnectToSQL  
- akhx.exe  
- SqlCommand  
- HangHoaMod  
- set_Padding  
- Binding  
- System.Runtime.Versioning  
- disposing  
- RuntimeTypeHandle  
- dtnamsinh  
- System.Data  
- AddData  
- UpdData  
- DelData  
- GetData  
- mscorlib  
- get_Email  
- set_Email  
- email

#### Dynamic Analysis

**Files created:**  
- C:\Users\vboxuser\AppData\Roaming\jrqJkPVjDOB.exe  
- C:\Users\vboxuser\AppData\Local\Temp\tmp196B.tmp

**Files opened:**  
- C:\Users\vboxuser\AppData\Local\Microsoft\Edge\User Data\Default\Login Data  
- C:\Users\vboxuser\AppData\Local\Microsoft\Credentials\DFBE70A7E5CC19A398EBF1B96859CE5D  

**Files attempted to open:**  
- C:\Users\vboxuser\AppData\Roaming\Mozilla\Firefox\profiles.ini  
- C:\Users\vboxuser\AppData\Roaming\Mozilla\SeaMonkey\profiles.ini  
- C:\Users\vboxuser\AppData\Roaming\Mozilla\icecat\profiles.ini  
- C:\Users\vboxuser\AppData\Roaming\Thunderbird\profiles.ini  
- C:\Users\vboxuser\AppData\Roaming\K-Meleon\profiles.ini  
- C:\Users\vboxuser\AppData\Roaming\Flock\Browser\profiles.ini  
- C:\Users\vboxuser\AppData\Roaming\Postbox\profiles.ini  
- C:\Users\vboxuser\AppData\Roaming\Waterfox\profiles.ini  
- C:\Users\vboxuser\AppData\Roaming\Comodo\IceDragon\profiles.ini  
- C:\Users\vboxuser\AppData\Roaming\Moonchild Productions\Pale Moon\profiles.ini  
- C:\Users\vboxuser\AppData\Roaming\8pecxstudios\Cyberfox\profiles.ini  
- C:\Users\vboxuser\AppData\Roaming\NETGATE Technologies\BlackHawk\profiles.ini  

**Scheduled task:**  
- Name: jrqJkPVjDOB  
- Trigger: At log on  
- Action: Start a program C:\Users\vboxuser\AppData\Roaming\jrqJkPVjDOB.exe

**Notable Registry Keys Added:**  
- HKLM\SOFTWARE\Microsoft\Windows Defender\Exclusions\Paths\C:\Users\vboxuser\AppData\Roaming\jrqJkPVjDOB.exe  
- HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\TaskCache\Tree\Updates\jrqJkPVjDOB\SD  
- HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\TaskCache\Tree\Updates\jrqJkPVjDOB\Id  
- HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\TaskCache\Tree\Updates\jrqJkPVjDOB\Index  

**Network Analysis:**  
- DNS Requests: Api.ipify.org  
- IP address: 192.0.2.123  
- Port: 443

#### Tools Used in Lab:

- PEStudio: Used for static analysis of the executable.
- RegShot: Monitored changes to the system's registry.
- Capa: Assisted in identifying capabilities and characteristics of the malware.
- Procmon: Monitored system activity in real-time.
- Wireshark: Captured and analyzed network traffic.

#### Overview:
The malware appears to be a PE32 executable with the file name "akhx.exe." The malware attempts to access sensitive data stored in browser and email client configuration files. It establishes persistence through a scheduled task that runs at logon. The malware makes DNS requests to "Api.ipify.org" and tries to communicate with the IP address 192.0.2.123 on port 443.
