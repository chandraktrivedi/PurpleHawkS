# Cyber Attack Defend (CAD) Intelligence

## Invoke-ShareFinder (PowerShell Network Share Enumeration)

  **INDICATOR**: ```Invoke-ShareFinder```
  
<details>

<summary>CAD Details</summary>

| TITLE | DETAILS |
| :-----------: | :-----------: |
| _PLATFORM(S)_ | Windows |
| _ARTIFACT(S)_ |  d3f:EventLog; d3f:NetworkTraffic; d3f:ScriptApplicationProcess |
| _COUNTERMEASURE(S)_ | d3f:NetworkTrafficAnalysis; d3f:ScriptExecutionAnalysis |
| _EVIDENCE(S)_ | edr:```Parent Process (powershell.exe) > Script Block Execution ("Invoke-ShareFinder")```; <br> siem:```Event ID: 4104 (PowerShell Script Block Logging), 5145 (Object Access)```; ```Sysmon Event ID: 1, 3, 17``` |
| _DETECTION_ | [PowerShell Share Enumeration Script](https://detection.fyi/elastic/detection-rules/windows/discovery_posh_invoke_sharefinder/) |
| _HUNT_ | ```(EventID:4104) AND (ScriptBlockText:"*Invoke-ShareFinder*")``` |
| _ACTOR(S) SEEN_ | SafePay |
| _MALWARE(S) SEEN_ | N/A |
| _REFERENCE(S)_ | [CISA](https://www.cisa.gov/) |

</details>

---
