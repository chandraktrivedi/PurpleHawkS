# Cyber Attack Defend (CAD) Intelligence

## ntdsutil.exe (Active Directory Database Dumping)

  **INDICATOR**: ```ntdsutil.exe "ac i ntds" "ifm" "create full C:\Windows\Temp\<folder_name>" q q```
  
<details>

<summary>CAD Details</summary>

| TITLE | DETAILS |
| :-----------: | :-----------: |
| _PLATFORM(S)_ | Windows |
| _ARTIFACT(S)_ | d3f:Process; d3f:File; d3f:EncryptedCredential |
| _COUNTERMEASURE(S)_ | d3f:ProcessLineageAnalysis; d3f:FileAnalysis; d3f:CredentialCompromiseScopeAnalysis |
| _EVIDENCE(S)_ | edr:```Parent Process (<process_name>.exe) > Child Process ("C:\Windows\System32\ntdsutil.exe" "<commandline>```; <br> siem:```Event ID: 4688```; ```Sysmon Event ID: 1, 11``` |
| _DETECTION_ | [Invocation of Active Directory Diagnostic Tool (ntdsutil.exe)](https://detection.fyi/sigmahq/sigma/windows/process_creation/proc_creation_win_ntdsutil_usage/) |
| _HUNT_ | ```(Image:"*\\ntdsutil.exe") AND (CommandLine:"*ac i ntds*") AND (CommandLine:"*ifm*") AND (CommandLine:"*create full*")``` |
| _ACTOR(S) SEEN_ | Storm-2570 |
| _MALWARE(S) SEEN_ | Qilin, DragonForce, Anubis, BERT |
| _REFERENCE(S)_ | [Microsoft](https://www.microsoft.com/) |

</details>

---
