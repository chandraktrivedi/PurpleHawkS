# IoAs
**Stager PowerShell:**
- PowerShell spawing Node.exe > NodeJS executing script
```
"C:\Users\{username}\AppData\Local\Nodejs\node-v18.17.0-win-x64\node.exe" C:\Users\{username}\AppData\Local\Nodejs\{filename}.js
```
- Node.exe installs
```
C:\WINDOWS\system32\cmd.exe /d /s /c ""C:\Users\{username}\AppData\Local\Nodejs\node-v18.17.0-win-x64\npm.cmd" install -g ws"

C:\WINDOWS\system32\cmd.exe /d /s /c ""C:\Users\{username}\AppData\Local\Nodejs\node-v18.17.0-win-x64\npm.cmd" install -g ethers@6.13.2"
```
- EtherHiding
```
C:\WINDOWS\system32\cmd.exe /d /s /c "powershell.exe -Command "[System.Globalization.CultureInfo]::InstalledUICulture.Name""
```
- Pesistance
```
C:\WINDOWS\system32\cmd.exe /d /s /c "powershell -Command "Set-ItemProperty -Path 'HKCU:\\Software\\Microsoft\\Windows\\CurrentVersion\\Run' -Name '49c7408a0393051a4bfd07c45e1c2353' -Value 'cmd.exe /c "C:\Users\{username}\\AppData\\Local\\Nodejs\\node-v18.17.0-win-x64\\node.exe" "C:\Users\{username}\\AppData\\Local\\Nodejs\\VfZUSQi6oerKau.js"'""
```

# References
[1] https://www.esentire.com/blog/muddywater-apt-tsundere-botnet-etherhiding-the-c2  
[2] https://app.any.run/tasks/6dba690a-4f8d-414e-aa21-49a09e384ce4  
[3] https://www.virustotal.com/gui/file/7ab597ff0b1a5e6916cad1662b49f58231867a1d4fa91a4edf7ecb73c3ec7fe6/behavior  
