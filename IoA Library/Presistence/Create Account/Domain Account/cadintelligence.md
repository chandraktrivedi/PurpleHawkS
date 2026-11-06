# Cyber Attack Defend (CAD) Intelligence

## New Account Persistence

  **INDICATOR**: ```net user <USERNAME> <PASSWRD> /add /domain``` OR ```net1 user <USERNAME> <PASSWRD> /add /domain```
  
<details>
  
<summary>CAD Details</summary>

| TITLE| DETAILS |
| :-----------: | :-----------: |
| _PLATFORM(S)_ | Windows |
| _ARTIFACT(S)_ | d3f:UserAccount, d3f:DomainUserAccount |
| _COUNTERMEASURE(S)_ | d3f:DomainAccountMonitoring |
| _EVIDENCE(S)_ | edr:```Parent Process (cmd.exe / powershell.exe) > Child Process ("C:\Windows\System32\net.exe" user <username> <password> /add /domain)```; <br> siem:```Event ID: 4688, 4720```; ```Sysmon Event ID: 1``` |
| _DETECTION_ | [New User Created Via Net.EXE](https://detection.fyi/sigmahq/sigma/windows/process_creation/proc_creation_win_net_user_add/) |
| _HUNT_ | ```(Image:("*\\net.exe" OR "*\\net1.exe")) AND (CommandLine:"*user*") AND (CommandLine:"*add*") AND (CommandLine:"*\/domain*")``` |
| _ACTOR(S) SEEN_ | Medusa, SafePay |
| _MALWARE(S) SEEN_ | N/A |
| _REFERENCE(S)_ | [CISA](https://www.cisa.gov/) |

</details>

---
