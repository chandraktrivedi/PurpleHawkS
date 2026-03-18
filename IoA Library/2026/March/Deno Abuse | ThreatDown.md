# Attack flow
**Stage 1:** Clickfix Attack  
**Stage 2:** msiexec.exe (.msi file) -> wscript.exe (.vbs file) -> powershell.exe (.ps1) -> curl.exe (download deno app) -> tar.exe (unzip)  
**Stage 3:** Deno.exe (c2 connection) -> cmd.exe -> powershell.exe (c2 connection) 
**Stage 4:** RAT palyoads

# IoA  
**Stage 3:** Using Deno as a Trojan horse to execute obfuscated JavaScript code
```
C:\Users\{Username}\.deno\bin\deno.exe" -A data:application/javascript;base64,{string}==
```

# References
[1] https://www.threatdown.com/blog/castlerat-cyber-attack-is-the-first-to-abuse-deno-javascript-runtime-to-evade-enterprise-security/
