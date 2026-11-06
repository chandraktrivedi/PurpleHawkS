# Cyber Attack Defend (CAD) Intelligence

## SyncAppvPublishingServer.vbs (Living-off-the-Land PowerShell Execution)

  **INDICATOR**: ```C:\WINDOWS\System32\WScript.exe "C:\WINDOWS\system32\SyncAppvPublishingServer.vbs" "<command_line>"```
  
<details>

<summary>CAD Details</summary>

| TITLE | DETAILS |
| :-----------: | :-----------: |
| _PLATFORM(S)_ | Windows |
| _ARTIFACT(S)_ | d3f:ProcessTree |
| _COUNTERMEASURE(S)_ | d3f:ProcessSpawnAnalysis; d3f:ProcessLineageAnalysis; d3f:ScriptExecutionAnalysis |
| _EVIDENCE(S)_ | edr:```Parent Process (explorer.exe / cmd.exe) > Child Process ("C:\Windows\System32\WScript.exe" "C:\Windows\System32\SyncAppvPublishingServer.vbs" <command_line>)```; <br> siem:```Event ID: 4688, 4104```; ```Sysmon Event ID: 1``` |
| _DETECTION_ | [SyncAppvPublishingServer Execute Arbitrary PowerShell Code](https://detection.fyi/sigmahq/sigma/windows/process_creation/proc_creation_win_lolbin_syncappvpublishingserver_execute_psh/) |
| _HUNT_ | ```(Image:"*\\wscript.exe") AND (CommandLine:"*SyncAppvPublishingServer.vbs*")``` |
| _ACTOR(S) SEEN_ | N/A |
| _MALWARE(S) SEEN_ | ClickFix |
| _REFERENCE(S)_ | [BlackPoint Cyber](https://blackpointcyber.com/) |

</details>

---
