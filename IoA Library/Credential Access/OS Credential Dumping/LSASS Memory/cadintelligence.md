# CAD Intelligence

## rundll32.exe (LSASS Memory Dump via comsvcs.dll)

  **INDICATOR**: ```rundll32.exe C:\Windows\System32\comsvcs.dll, #+000024 <PID> \Windows\Temp\<random>.<ext> full```
  
<details>

<summary>CAD Details</summary>

| TITLE | DETAILS |
| :-----------: | :-----------: |
| _PLATFORM(S)_ | Windows |
| _ARTIFACT(S)_ | d3f:CreateProcess |
| _COUNTERMEASURE(S)_ | d3f:ProcessSpawnAnalysis |
| _EVIDENCE(S)_ | edr:```Parent Process (cmd.exe / powershell.exe) > Child Process ("C:\Windows\System32\rundll32.exe" C:\Windows\System32\comsvcs.dll, #+000024 ...)```; <br> siem:```Event ID: 4688, 4624```; ```Sysmon Event ID: 1, 13``` |
| _DETECTION_ | [Process Memory Dump Via Comsvcs.DLL]([https://detection.fyi/mbabinski/sigma-rules/2024_redcanary_threatdetectionreport/technique_rundll32_suspicious_export_functionalities/](https://detection.fyi/sigmahq/sigma/windows/process_creation/proc_creation_win_rundll32_process_dump_via_comsvcs/?query=comsvcs)) |
| _HUNT_ | ```(Image:"*\\rundll32.exe") AND (CommandLine:"*comsvcs.dll*") AND (CommandLine:"*#+*")``` |
| _ACTOR(S) SEEN_ | Medusa, Akria |
| _MALWARE(S) SEEN_ | N/A |
| _REFERENCE(S)_ | [The DFIR Report](https://thedfirreport.com/); [CISA](https://www.cisa.gov/) |

</details>

---
