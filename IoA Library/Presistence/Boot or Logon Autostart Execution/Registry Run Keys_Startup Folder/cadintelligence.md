# Cyber Attack Defend (CAD) Intelligence

## Startup Folder Persistence

  **INDICATOR**: ```C:\Users\<username>\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup\<startup_script>```
  
<details>
  
<summary>CAD Details</summary>

| TITLE| DETAILS |
| :-----------: | :-----------: |
| _PLATFORM(S)_ | Windows |
| _ARTIFACT(S)_ | d3f:UserStartupScriptFile |
| _COUNTERMEASURE(S)_ | d3f:SystemInitConfigAnalysis |
| _DETECTION_ | [Startup Folder File Write](https://detection.fyi/sigmahq/sigma/windows/file/file_event/file_event_win_startup_folder_file_write/) |
| _HUNT_ | ```(TargetFilename:"*\\Start Menu\\Programs\\Startup\\*") AND (TargetFilename:"*.vbs" OR TargetFilename:"*.bat" OR TargetFilename:"*.ps1" OR TargetFilename:"*.lnk")``` |
| _ACTOR(S) SEEN_ | N/A |
| _MALWARE(S) SEEN_ | TASK#STOMP |
| _REFERENCE(S)_ | [Securonix](https://www.securonix.com/) |

</details>

---
