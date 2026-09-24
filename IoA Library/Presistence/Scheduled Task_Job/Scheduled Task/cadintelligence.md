# Cyber Attack Defend (CAD) Intelligence

## schtasks.exe (Scheduled Task Persistence)

  **INDICATOR**: ```schtasks.exe /create /tn "<task_name>" /xml "C:\Users\<username>\AppData\Local\Temp\<task_file>.xml"```
  
<details>

<summary>CAD Details</summary>

| TITLE| DETAILS |
| :-----------: | :-----------: |
| _PLATFORM(S)_ | Windows |
| _ARTIFACT(S)_ | d3f:Process; d3f:ScheduledJob |
| _COUNTERMEASURE(S)_ | d3f:ScheduledJobAnalysis; d3f:ProcessLineageAnalysis; d3f:ProcessSpawnAnalysis |
| _DETECTION_ | [Scheduled Task Creation Via Schtasks.EXE](https://detection.fyi/sigmahq/sigma/windows/process_creation/proc_creation_win_schtasks_creation/) |
| _HUNT_ | ```(Image:"*\\schtasks.exe") AND (CommandLine:"*/create*") AND (CommandLine:"*/xml*")``` |
| _ACTOR(S) SEEN_ | N/A |
| _MALWARE(S) SEEN_ | TASK#STOMP |
| _REFERENCE(S)_ | [Securonix](https://www.securonix.com/) |

</details>

---
